---
title: "The One with Learnings From Dev Exchanges"
date: 2020-05-25T13:15:53+02:00
tags:
- studitemps
- people
- product development
---

We revived our dev exchange thingy last week. I'm not going to get too far into what we do and how we got the idea to do this because we have written about this on our [tech blog](https://tech.studitemps.de/blog/2019/06/13/dynamic-teams-austausch/) when I did my first one, but basically, a dev from one team can spend some time in another team in order to learn something specific, exchange some knowledge and improve our work together. I've done this twice before by joining my current team for 1 or 3 days when I was in my previous team. This time, it's again been someone from my previous team joining my current team, for a week.

Since I've now been part of this exchange 3 times, I can now comfortably say that this is the single best thing we ever started in our department and I'm going to explain why in a bit more detail, but the main points are:

- The person who goes into the other team can take so much inspiration from a different way of working back to their team. That can be little things like using Slack for meetings calls because you can draw on a shared screen or bigger things like how a meeting is structured.
- The team gets an outsider's view on their way of working. That can be reassuring and/or it can highlight problems the team itself would have never been able to pinpoint because they are too close and have been doing it like this for a long time.
- Pairing with someone who is not used to your code and architecture forces you to think about why you do certain things and how they are done which can lead to understanding your own application much better.
- Explaining the whys and hows leads to an exchange about how these things are done in the other team and usually both parties then find something to improve in their own code and application structure or their understanding of it, and it might even lead to a talk about the interfaces between the two teams and how these can be improved.
- Pairing with someone you don't usually pair with lets you learn a lot more about your personal way of (and problems with) testing and coding than pairing with someone who's way and style you have been influenced by.
- And last, but certainly not least: A lot of knowledge, inspiration and a feeling of togetherness (which is crucial for developing a software product together across teams) is gained from informal conversation. This lets you have coffee chats with someone you might not usually talk to a lot.

I'm going to try to add some examples for some of these points, mostly from this last exchange.

### Taking back inspiration to your own team

I remember from my last two swaps to my current team that I liked the way they structure their workflow within Jira and GitHub. It seemed a lot more fitting for my way of working and I tried to implement some of it in my team back then.

Often it's the little things that make the most difference. Our team has been used to having someone work from home for a while so we have built some expertise in doing remote meetings now. I think what impressed Andreas the most was how we use Slack for our meetings calls. We always have someone sharing the screen (and we sometimes swap if it makes sense) with a ticket we are going to refine, mockups or models for a new feature or even our application in its current state. Slack lets you draw on a shared screen and we use this heavily to make up for the fact that we are not in a room together.

We draw fun party hats to celebrate when someone is done with a ticket or someone got good feedback from the outside. In a room together, you'd use thumbs up or clap or just a big smile. We draw checkmarks if we agree with what someone says. We ask "has everyone understood this" or "does anyone have any more questions" and draw checkmarks and X to give a reply. In a room together, you'd say "yep" or just nod your head. And we draw on a mockup or application screen to show what we are talking about or how we would do things. Sometimes we even draw quite elaborate models with Slack's drawing thingy and then screenshot this when we are not in a modelling tool together. In a room together, you'd go to a whiteboard to draw something to get a better understanding. It's the tiny little things, but I think they make a big difference. It's actually something we are very aware of. When we have to do a call somewhere else because we are too many people, we miss the drawing tool a lot.

### Understanding your own application better

Our application has been running for 4 years (in various forms) now, so there are a lot of shortcuts that make writing standard code easier for us. But sometimes that makes you forget how things actually work and then it's kind of a pain in the ass to figure out how to do something that deviates from the norm.

When pairing with someone who doesn't know how these things work, you need to explain the magic that is happening behind the scenes. This time, it went one of three ways:

- I thought about how I'm going to show Andreas what I had done for the first part of the feature I was working on in order to explain how we are going to implement the second part. I went through my usual test/implement flow from the outside in and pointed out some things that are interesting.
- He said "Hold on, where is this event coming from? Did we do anything to make it appear?" and I said "Oh yeah, so this is our CommandHandler class and it does this cool thing ..."
- He asked the question and I said "Ooooh. I have no idea, it just works? Let's find out how!"

In all three cases we then looked at the behind-the-scenes code and I tried to explain what is happening (or he figured it out faster than I did and I understood some more than before).

If I need to use these things in a different way in the future, it will be easier for me to find where the code is hidden and how I can apply it to my situation.

### Understanding both applications better

We have a certain way of handling commands/events and it's really easy for most cases, but there is some setup that seems a bit weird if there isn't a lot of business logic involved. And the way we handle business logic inside our command handlers seemed weird to Andreas. We then talked about how they are doing it (I remembered a bit, but not everything) and then realised that our applications just handle very different kinds of domain logic in general. I think we both had never thought about this particular difference and I guess it will be valuable to have gained this understanding for both of us in the future.

On Friday we did a mob code review with the other dev in my team, Sascha, and talked about some things we had noticed during the days before. One thing in particular was how we have different ways of handling causation in (external) events. I don't think we had ever thought about the issues that might arise with our way of doing this and will talk about this in our team a bit more when the other guy is back.

### Learn about your way of writing code

I noticed two big things:

I sometimes (especially with deadlines looming, see [last post](/posts/2020-05-23-deadlines)) give up too quickly when I get stuck. If I'm working on my own, I call Sascha, explain my problem and let him point me to the right part of the application. If I'm in a pairing session with one of the guys from my team, I just say that I'm lost and they help me out. I didn't do this while pairing with Andreas, because it would have been a bit weird to add Sascha to the call 3 times. And maybe a bit because I didn't want Andreas to see how often I ask for help. I just told him that I'm not sure what's going wrong and where to go from there. And he just said "Ok, let's find out together, where is the super class for this thing, let's have a look at it." And I realised that it's not that complicated most of the time. I think my mind is sometimes still stuck in "I'm stupid, I don't know anything on my own" mode and refuses to just take the next step. But I can now actually do this, so I should do it more often.

There was a test that was a bit complicated because it tested a command handler that needed to react to errors that might come from two different places a bit more deep inside the application, so I needed to mock/stub some of these parts. And my test wasn't structure very well so we both got lost in terms of what we are actually testing right now a few times. But the way Andreas asked me why I am stubbing this call or using some double made me realise that I actually have no clue what I'm doing there. My way of working through a ticket starts with thinking of something similar, finding a test for this, copying the test and then changing stuff in order to set up a test for what I'm doing. And when I get stuck, I call the other guys for help, they know what the test is supposed to be doing and tell me what I have missed. So I never noticed how big my knowledge gap in terms of testing actually is. Pairing with Andreas has made a small known unknown a lot bigger and I now know that I should really focus on improving my knowledge about testing methods.

### That informal stuff

Now this was actually really the least important thing coming out of this particular instance of the exchange program because Andreas and I just talk a lot anyways so I don't think we gained a better understanding of our particular ways of working/communicating or improved our relationship a lot. But it was immensely fun to be able to spend a few days working with someone I admire and like a lot and who I really miss working with on a regular basis.

But what I remember from the last two times was that after spending a day or two with someone from another team you don't usually talk to a lot, it's so much easier to go to them when questions arise about things that concern both teams. We have a lot of #teamA_teamB slack channels for these kinds of questions, but sometimes it's just easier to go to someone directly and ask for their input or help. And that in turn is a lot easier with someone you know a bit better.

## tl;dr

Changing teams for a short amount of time and working with someone from outside your team helps both teams improve their way of working, both structurally and technically. It also improves formal and informal communication between the teams.

So far, only two people have used this opportunity and it was the same team they did it with. I hope we'll do more of this soon. I'd love to have someone from another team (not my old one) joining our team for a while, because I guess there is even more to gain for me personally by pairing with someone who's way of working and applications I know next to nothing about. And I'd love to join a different team for a while. Maybe our data team, or the team that does a lot of mobile app development, because that's something I know very little about.