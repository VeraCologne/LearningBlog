---
title: "The One with a Dev Swap"
date: 2019-05-15T16:13:53+02:00
tags: 
- studitemps
- people
---

One of our action items from last quarter's department retrospective was to start an exchange program where people can join a different team for some time. So today I'm spending half a day with one of our other scrum teams. 

In the morning we talked about what we want from this program: 

1. Learn from other teams: See what they do differently or which other techniques/technologies they use so that each team can improve their own work a bit.
2. Make it easier for people to move between teams. Right now we don't lend people to other teams very often. It sometimes happens that people move to a different team, but they usually stay there for a longer time. In my opinion, it would be great if we were able to do this more spontaneously, for example when one team needs a bit more help or when someone just wants a change for a while.

My buddy for today, John, also asked me some questions about team work, my impression of their team and my expectations for the day, and he explained to me what we were going to do: A refinement meeting and pairing on the ticket he started working on yesterday.

The refinement meeting surprised me: Instead of talking about, refining and estimating user stories, 2 of the devs presented what they had done in days before: re-implement a part of their application with Vue.js and a GraphQL client. They talked about the structure of their code, problems they ran into and how they might solve them, how to test this and what to test and other use cases they might have for this technology. They also discussed some UX/UI questions for one of the actions but it was mostly very technical. I later asked if that's what they usually do. It's not. They just had the need and the opportunity to try out a different way of presenting this one part of their application that has become a bit slow, so they did some kind of a spike and used their daily refinement meeting to give a status update and figure out what else they need to do before they can release this. They usually use their refinement meeting to refine user stories, just like we do.

Afterwards I started working on a feature with John. He first explained their workflow for tickets/tasks which is a bit different from ours and then their coding/git/CI flow which is very different from ours. Then we got into the code. This team's programming language is Ruby which I know only a bit about. The few things I know are from my work (as mostly a tester) on an application here at Studitemps that isn't used anymore but that was the basis for this team's application, so I could still remember some of the concepts and structures (that they are in the process of moving away from). And it's just true that Ruby, just like Elixir, is very easy to read so I did not get lost a lot. 

While moving through the different parts of the application that needed to be changed for this new (small) feature, we talked about how the structure of our code is different from theirs, the pros and cons of using translation files for an application that has only one language, how they use Policies (and how I have no idea if we have something comparable or if we even have the need for something like a Policy), how name spaces and named arguments are different in Ruby and Elixir, how much of the outer layers of an application are very similar in Rails and Phoenix (routers, migrations etc.) and about command busses/handlers and application services.

In the afternoon we wrote tests for the features which also led us to talking about how we test: 

- Test first/last: John writes implementation code first and tests last, I try to write tests first and I think the rest of my team does this even more than I do. 
- Outside-in vs. inside-out: He usually starts with unit tests, in my team we have one person who starts with unit tests and one who starts with the most-outside test possible, I do a mix, I think (see [The One where I Struggle With Outside-In TDD](/posts/2019-01-23-outside-in-tdd)).
- How to make sure your test tests what it is supposed to test: Especially when writing tests after the implementation, how do you make sure you don't have a false positive (by changing the expected return value usually).
- Testing events: Which fields of the events do we test? How do we test internal vs. external events? 
- Running the test suite: He runs only the test file he added/changed because running the whole suite takes too much time. He then pushes his changes and later checks if his build is red. That only works when you are working on your own in a feature branch, I guess. And fortunately, most of our applications are so small that running all tests only takes as long as checking if there are any new slack messages. 

Afterwards we talked about whether my impression of their team had changed (no, not during these few hours), what we liked and disliked about this day and what we would change for the next time. I actually didn't dislike anything but I would try some other things next time. First, we deliberately chose this short time frame for today in order to keep the overhead small: no big preparations and just a short heads-up to the rest of the team for missing half a sprint day. Next time, I would like to spend at least one whole day there and definitely take part in their daily standup (I had another meeting at that time today) and do some coding myself. Today he did all the typing which was nice because I think it would have stressed me out to write Ruby code this first time. We both agreed that this was a good first try and that we will lobby for team exchanges to be done more frequently. I think we are going to talk in a bit more detail about the structure of this during one of our next learning hours. 

Aside from a lot of input and food for thought about code structure, tests and team communication, there were also some very concrete and practical things we learned today that will vastly improve our productivity: John learned how to write an umlaut easily with a US keyboard layout and how to copy the current file's path in VS Code in order to run the tests in this file and I learned how to close the current tab. And most importantly: I learned how to make coffee that tastes ok with our weird coffee machine! I had always made something with espresso beans because that's what I usually order when I go for coffee, but you actually need to choose a coffee that uses the regular coffee beans! 

