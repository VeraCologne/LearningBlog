---
layout: post
title:  "The One Where I Struggle With Outside-In TDD"
date:   2019-01-23 22:13:47 +0100
tags: 
- testing
---

I have been trying to work my way into our application from the outside. We do Specification by Example (or at least trying to do some version of it), testing mostly what the user would see. And I do see a benefit in starting with a specification/feature test, and going deeper inside once the test is not giving me enough feedback anymore. So I try to implement every feature by writing the specification test first, then going to an application test, then the domain-service test and then back.

But I struggle. I always get lost. I think part of it is that it really stresses me out to have so many uncommitted files and red tests lying around. I don't want to start mocking everything (and I wouldn't really know how to for every step, anyway). And I don't feel like it really helps me understand the feature better because I think I am trying to keep everything in my head at once.

It also makes it incredibly difficult to ask for help when I have been staring at a problem for too long. I am always somewhere deep in the middle of chaos and I can't really explain my problem, what I have been doing and what I was about to do. And then I start to question everything and this gets just plain unhealthy.

I guess I should spend some time figuring out how to get out of this, but today is not the day.
