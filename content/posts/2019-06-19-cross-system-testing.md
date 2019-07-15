---
title: "The One with Cross-System Testing"
date: 2019-06-19T16:00:53+02:00
tags: 
- studitemps
- testing
- rails
---

Today was the last day of the second edition of my team swap. We did not have much time for coding today, but instead I learned a bit more about how they use their test environment and deploy once they are done testing. 

At first, we took care of the ticket we finished implementing on Monday. We had put it on Staging on Monday and tested it by ourselves (finding a little bug in the process that hadn't been caught by tests). Then we flagged the ticket in Jira to indicate that it should be tested by others, and also asked another team's tester to take a look at it. That's what we usually do when we have risky changes that affect more than one team's application. On the one hand, it is easier to test how changes are handled in one's own system and on the other hand this sometimes helps bring a fresh perspective and catch problems nobody in your team thought about. This morning, we deployed it to Production in order to have Staging free for yesterday's ticket. They deploy in a similar way to us, but annotate their releases in Github much more thoroughly. And they use a changelog service to inform their users about important changes and gather feedback. That's both very interesting but nothing for us right now because our group of users is much smaller than theirs and they all sit a few rooms away from us, so direct communication trumps fancy changelogs. 

After deploying, we put our changes from the ticket we worked on together on Staging and started testing. The ticket was about consuming events from another application (that had already been deployed to Staging), so we could test the integration between the two applications. We noticed right away that it didn't work but also that the integration in general would work. The issue was just a small typo that the devs from the other team could fix immediately. 

In the afternoon, we quickly implemented another ticket about showing one of the newly added attributes to the user. Their frontend dev had already done the ground work, we just needed to make it dynamic depending on the object's state. To be honest, I don't really understand what we did there because it was a lot of Rails stuff, frontend stuff and helper functions. 

But all in all, I think these 3 days have been a huge success for me. It was interesting to work with somebody else who does things in a different way, again. I learned a bit more about how their team works, how their applications work and how to do things in Ruby/Rails. And I think there are lots of things that I need to reflect on a bit more and talk over with others which will lead to me learning even more from this experience. Right now, I'm too tired to do that. As fun as this all is, being in a different environment and doing novel things is definitely more exhausting than business as usual. But I'm certain that this concept is great for me and for our whole department and I look forward to doing this again (maybe in the autumn months and maybe with a full sprint next time?)
