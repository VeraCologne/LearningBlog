---
layout: post
title:  "The One With Architecture Decision Records"
date:   2018-11-29 19:43:47 +0100
tags:
- architecture
---

Today I learned about Architecture Decision Records and MECE for structuring lists in our department-wide Learning Hour that we do every other week.

We have been using ADRs before in our team and there was actually a problem in our application two days ago that made us create another one. Architecture Decision Records consist of
- Title
- Context
- Decision
- Status
- Consequences

and they are used to document decisions in order to be able to still understand them later on.

A lot of times, things in software development have been decided by someone a very long time ago and nobody knows why, anymore. This leads to either blindly accepting the decision (although there might be much better options available now) or blindly changing it (although there might have been very good reasons that the one who changes it will experience later). Having a record of these decisions with a context, discarded options and consequences helps a developer who wants to change a decision figure out if that is a good idea.

In our case, it was the rather simple problem of naming modules and folders. Our domain language and thus must of our code is in German and I realised that we were sometimes using an imperative and sometimes and indicative form (there is no difference in English). We could see in our code from our last application that we were using the indicative form but we couldn't remember why we decided to do that. So we brainstormed some reasons why the indicative form is better (no splitting of compound verbs, object at the beginning) and wrote an ADR to document that we have decided on this form and why. We haven't really made up our minds about methods right now. I kind of prefer the imperative version, but it might look weird. We will see.

### Things I don't really know much about: (today: events edition)
- Event publishing/consuming. This time specifically RabbitMQ and its exchanges and queues.
- Event structures. I tried to define some more events today and I'm not really happy with a lot of it.
- Political events in the past. We did a games night after work that was really, really fun. We played Bezzerwizzer and apparently politics is not my forte. I'm happy to leave it like that for now, though.
