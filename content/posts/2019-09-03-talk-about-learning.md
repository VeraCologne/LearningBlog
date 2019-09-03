---
title: "The One where I Talk About Learning"
date: 2019-09-03T08:55:53+02:00
tags:
- studitemps
- learning
- apprenticeship
- elixir
- phoenix
- ruby
- rails
---

I talked to two people about my learning path yesterday. The first was one of my former team mates who I showed my idea for my learning project and asked if he would help me implement it. My idea is to have an application where I can track what I learn in a structured way.

At SoCraTes I talked to 2 of the HolidayCheck apprentices about their program and I showed them my messy matrix on things to learn. Afterwards I condensed it down into Topics and Subcategories (so 2 instead of 3 levels). The Topics are Software Design, Testing, Agile Methods, Communication & Teamwork, Learning & Productivity, Tools and Languages & Frameworks. The first 6 are taken from HolidayCheck's apprenticeship program, but I added Teamwork and Productivity. I'm not sure if teamwork fits yet, but that's one of the things I'm going to get feedback on in the next few days. I added the topic Languages & Frameworks to contain those languages and frameworks we use at Studitemps in order to make it a training program for software developers at Studitemps, not a generic apprenticeship program.

There are 4 to 8 subcategories for each topic, some of them taken from the second level of my previous skills matrix and some of them from what HolidayCheck uses as subcategories. I'm not sure about all of them yet though. One of my main goals for the next few days is to finalise this list with input from some of the other people here.

The first main feature of my application will be a way to track one's learning by providing a subcategory and optional context. So if I continued reading Head First Ruby today, I could add "Ruby: Exception Handling" (with Ruby being a subcategory of Languages & Frameworks) and I could later see what I did today, how much and when I learned about Ruby and so on. I want to store this information in a way that makes it easy to analyse it later, maybe by adding graphs for topics and subcategories (no idea how to do this yet, but we'll see). For the first step, I'd be satisfied with something that I can just query the database about.

If I have this, my MVP would be done and useful to me. Further steps could be to have a website that provides an overview on the whole training program and its contents, maybe even with added resources and people a learner could ask for help when they are stuck. And a fun thing could be to show a message when a user logs in like "Hey Vera, you haven't paid attention to Testing in a while. How about learning a bit about TDD today?", by analysing which category was tracked the least in the past weeks/months. But that's light years away, I guess. And I have no idea if anyone besides me would even use this.

I want to implement this as a Phoenix application, that's why I asked one of my former team mates for help. In the past 9 months or so I tried implementing a small Phoenix application as a learning project, while simultaneously working on productive Phoenix applications with very advanced concepts and that didn't work for me. So I'm now trying to split this differently: I will learn Ruby/Rails by reading books, doing tutorials and working on this productive application while talking to my team mates about what my biggest gaps are and what I should focus on next. And I will learn about Software Design, Testing and much more in general by implementing something in a different language (that I already know and like). I hope this works better. The first steps are done: My former team mate likes the idea and is willing to carve out some time for me to ask questions about Phoenix stuff. I will also ask one of my current team mates for help on more general things.

And then I also talked to Sascha, from my current team, about getting up to speed (it will a long time, but that's fine) with Ruby/Rails and our application. I told him that I think the Head First Ruby book is a bit too basic for me and he suggested Domain Driven Rails, which is already on my list of books to read. This book should help me understand most of the concepts of our application, if I'm already a bit familiar with standard Rails concepts. I'm not sure I am, so he suggested doing something like Code School's Rails for Zombies course to quickly brush up on my knowledge. So I think I'll skim-read the last few chapters of Head First Ruby, then do Rails for Zombies (again, I have already done once this years ago) and then I'll dive into Domain-Driven Rails.

I guess these things will occupy me for a while ...