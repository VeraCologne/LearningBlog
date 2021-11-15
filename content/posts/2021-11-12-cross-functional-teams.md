---
title: "The One with Cross-Functional Teams"
date: 2021-11-12T15:10:53+01:00
tags:
- pragprogwrimo
- software architecture
- events
---

I managed to see a stream from [software-architektur.tv](https://software-architektur.tv/) live today. A coworker and I watched it together in an Around call and I think we are going to do this more often from now on.

Today's talk did not bring much new information to us, but I still think it's important to talk about or hear about things like this every once in a while. The stream was announced as "Cross-funktionale Teams zielgerichtet in den Abgrund stürzen" (Throwing cross-functional teams into the abyss, I guess?), but most of the talk was about what it means to be a cross-functional team, where you have the boundaries and why you want cross-functional teams (and why you might not).

The main benefit mentioned by [Sven Johann](https://twitter.com/kaesfiehs) is that a cross-functional team can decide on their own what to do and how to do it, without needing to wait for outside information or help. This makes them faster, which is great if you want to experiment and get quick feedback. The autonomy that a cross-functional team has is therefore a means to an end and not the goal of having a cross-functional team. And autonomy is always subjective and cannot mean anarchy.

A drawback of a cross-functional team is that it might be more expensive because you might be missing experts for specialist things like security and testing which were traditionally done by a different team. Having the developers do this might take them longer or they might need help from outside consultants. A solution for this problem might be having specialist teams inside the company who can consult the feature teams on those topics and enable them to learn more about these through this internal consultation.

Antipatterns mentioned were:

- too much focus on the wrong aspects of autonomy, because speed is the goal and not "I can do anything I want to do"
- running after the trend "cross-functional teams" although speed is not what you need, for example in a very stable, traditional environment
- blindly copying what Amazon does or what someone in a Youtube video said
- doing this without consulting with the teams first: maybe they don't want to be t-shaped but rather have their specialty and focus on that

Some suggestions for what people should do if they want to do cross-functional teams or have problems with how they are doing them:

- read [Team Topologies](https://teamtopologies.com/book) (I guess I should really do this now, it has been mentioned in about every other talk I saw this year)
- build Communities of Practice for specialist topics that people inside cross-functional teams want to or should learn more about
- talk to their managers about what the goals actually are and what impedes them from achieving those goals

In the end, they talked about what this has to do with software architecture and an architect's job and that kind of repeated a lot of what was said in [last week's talk](/posts/2021-11-06-architecture-and-organisation): Things like operations, security and UX are architecture topics, senior devs and architects have to make sure these things work. And if someone decides how teams are structured, they are essentially building the architecture, so managers need to understand architecture and architects need to understand organisation design. The main goal of organisation design and architecture is to structure and organisation/system in a way that people are able to handle their tasks and to improve the system.

That last aspect has been kind of a big topic in my bubble this year and I'm still not quite sure what to make of it. Especially in flat-ish hierarchies and without dedicated architects.

Oh and Sven advertised going to [InnoQ's technology day](https://technologyday.innoq.com/) which had already been on my list before and now I'm registered to attend for real.

To finish this, here are some resources mentioned during the talk:

- Jez Humble. [Continuous Delivery](https://continuousdelivery.com)
- Gerald Weinberg. [The Secrets of Consulting](https://leanpub.com/thesecretsofconsulting)
- Matthew Skelton and Manuel Pais. [Team Topologies](https://teamtopologies.com/book)
- Paul Watzlawick. [Anleitung zum Unglücklichsein](https://www.buecher.de/shop/buecher/anleitung-zum-ungluecklichsein/watzlawick-paul/products_products/detail/prod_id/20939158/)
- Gregor Hohpe. [Enterprise Architecture = Architecting the Enterprise?](https://www.youtube.com/watch?v=mS0AJLqmnvQ)
