---
layout: post
title:  "The One With Refactoring"
date:   2019-02-13 17:13:47 +0100
---

In my mentoring session today we talked about reviewing my code. We work trunk-based and I find it very difficult to prepare for code review. Once I am "done" with something, there have been so many commits in between mine that it's hard for me to gather everything and look back at it on my own and with someone else. It was easier when we did feature branches because then I could just do a pull request against develop and I would see all MY changes. We are looking for a better way of doing this.

Then we looked at what I had been doing the past few days. My coworker looked at my left_join where: is_nil solution and said "Why are you not using on?" Oh. Yeah well, databases.

Then we spent some time optimising a URN function that I could have used for an event consumer had it not been too specific. We are creating URNs that consist of our domain, the context, the entity name and a UUID in all of our applications, but this function would only take an entity name. We wrote 3 new functions:
- one that takes a context name, an entity name and an ID to create a URN with these and our domain
- one that takes an entity name and an ID, gets the context from the application it is in and calls the function with 3 arguments
- one that takes an entity name, generates a UUID and calls the 2-argument function

We first brainstormed which functions we would need, wrote tests and implemented the easiest ways to make them pass. Then we took a look at our tests again and realised that one function isn't actually really useful but we would need a different one which we then implemented. Then we started refactoring the disparate functions to better work together.

I learned something about getting an app name from a mix project and that I had better implemented the 3-arity function first (I did it the other way around) beause that would have shown me refactoring possibilities earlier.
