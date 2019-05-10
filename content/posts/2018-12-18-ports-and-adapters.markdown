---
layout: post
title:  "The One With Ports and Adapters"
date:   2018-12-18 20:43:47 +0100
tags: 
- architecture
---

In my quest to learn more about software architecture I have read about Hexagonal or Ports and Adapters architecture in [Implementing Domain-Driven Design](https://www.oreilly.com/library/view/implementing-domain-driven-design/9780133039900/) today. After reading, I took some notes on the main features of this architecture pattern and added some a screenshot from the book to help me remember everything better and to be able to discuss this in one of my review sessions.

I remembered that I had bookmarked a graphic on Ports and Adapters and something with DDD a while back that I used to draw a model of the use case of our latest application, so I added this as well. I also clicked through to the article the graphic was from because I had only bookmarked the search result image and it was [this one](https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/). When I read the title, it rung a bell, but I wasn't able to connect it. A few moments later, Slackbot reminded me of an article that I wanted to read from the Software Crafters Slack and there it was. Funny coincidence.

I will read the whole article tomorrow and will also brush up on my knowledge about cognitive biases, because I'm sure there is one about interesting coincidences that we apply too much meaning to. I'm also pondering the difference between an adapter and an ACL. Are they the same? Are they similar?

#### Things I don't know much about
- Dependency Injection: I also read the Layers architecture part from the iDDD chapter on architecture and they talk about the Dependency Inversion Principle which can be achieved via Dependency Injection. Also, one of my co-workers will use our next code review to show us how he used Dependency Injection for better integration testing of Event Publishers. I have zero clue what that means.
