---
layout: post
title:  "The One With People and Processes"
date:   2018-12-17 16:43:47 +0100
tags: 
- people
- testing
---

In the past few weeks our main focus was on integrating two of our bounded contexts with each other. We are in the last months of getting rid of a grand old monolith and replacing it with a domain-driven, event-focused, modular architecture. Our team has spent a good part of this year on an application that generates bills for our clients and since this is at the very end of our business process, we built it so that it integrated with the old monolith so the users were able to test it way before the core domain applications were built.

Now we have to integrate it with this other application and we decided that the best way for now is to load an iFrame of the billing application into the application where orders are created and have this application consume the events from the billing application in order to show some of this data to users or use it in contracts.

The billing application is event-sourced and already persists events for everything users do, but we did not publish most of them because there was no application that needed it before. Implementing these published events was very easy, because you only had to listen to the events that were already being published internally and map them to external events to be published to RabbitMQ.

The tricky part was writing integration tests for this. Because somewhere during the time we worked on the billing application, we decided there was a better way to write application services and half of the entities that we gather from user input have a different implementation than the others. When I wanted to test if the events were published, I wrote integration tests that started from theses application services. And this took a while. The implementations were really different and it became apparent when I was writing the tests. I vented about this in our team channel and we talked about this in my mentoring session today.

To sum it up: It's a people problem. And a process problem. We have very different views on how to build a product like the one we are building in our team. Which can be a good thing because this is how people learn and how products get better. But although we talk about not being happy with something and start implementing something new in a different way, we don't have (or take?) the time to review this properly and make a decision on how to proceed from there. We should ultimately decide on one way of implementing things, write an [ADR](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) and change everything that does not adhere to our decision.

#### Things I don't know much about
- Making architecture decisions while being short on time and taking care of everyone's opinion
- Ecto.Multi. I somehow crawled my way throug a multi run today but I don't really know why or how it worked. I will continue reading the Ecto book and see if I can learn more about Multi from there.
