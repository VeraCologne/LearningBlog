---
layout: post
title:  "The One With Agents and Supervisors"
date:   2019-03-14 08:13:47 +0100
---

Yesterday I spent the whole day on finishing up my end-to-end test for an event publisher that I had written on Monday and on working through the gigantic amount of change requests for my pull request.

I got my test to work early in the morning but running the test suite threw up tons of lines of error messages. The tests all passed but something was obviously going wrong. My EventPublisher was terminating because the process of our EventPublisherStub wasn't alive. Oookay?

I looked at this for a while and then gave up and asked for help. Together with my coworker we added a function to look for a published event to the stub and one to override the child specification and then we started it for all integration tests. Then we stopped the default Publisher for the event I was working on in my end-to-end test before starting it again with our RabbitMQ Event Publisher instead of the stub because we are actually testing this there.

This last paragraph still does not make a lot of sense to me. I think that the test was looking for the publisher stub to be running because that is the default client for all event publishers and since I was talking to one of the publishers it expected the stub process to be running which it was not. Since I had explicitly started the RabbitMQ client, the test worked but it was now trying to connect to both and couldn't. So after we started the stub process for all integration tests and then stopped the actual publisher and started it up again with the RabbitMQ publisher as its client instead of the default stub, it worked.

The stub is actually an Agent because in order to test for published events you need something that holds some kind of state in a functional language and that is what Agent are for. When its publish function is called, it updates its state to add newly published events to any events that have already been stored.[^1] Before being able to do that, it needs to start itself (the documentation for `start_link` says it "starts an agent linked to the current process (with the given function)" – what process?). It runs under a supervisor as a child which can be specified by using `child_spec`.
tl;dr: An Agent saves and updates a state for a process which can then be accessed and modified from outside of it. (Am I right here?)

I am struggling to understand what a Supervisor does. It apparently has something to do with how processes are started and stopped for an application. Maybe so that the right ones are running when other processes need them? The first 2 lines of the docs are, um, great? "A behaviour module for implementing supervisors." Yeah thanks. A supervisor implements supervisors. Let's read on "A supervisor is a process which supervises other processes." Well now we have the common definition of a supervisor in any context. Let's skip some lines and go the the Example section: "... we will define a GenServer that represents a stack" Okay, I'm out.

I think I succeeded in learning a bit more about Agents and Supervisors. A tiny bit. And I have some questions and points of interest that I can use to look and ask for more information. That sounds good.


---

[^1]: I guess the fact that this sentence shows up as completely underlined in red in my editor tells me that I am still not understanding and phrasing it in a way that makes sense.  
