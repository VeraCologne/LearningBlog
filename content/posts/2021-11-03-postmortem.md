---
title: "The One with a Postmortem"
date: 2021-11-03T19:50:53+01:00
tags:
- pragprogwrimo
---

We did a postmortem today for an incident we had during Allerheiligen. It wasn't something really really bad but one of our internal apps crashed our AMQP instance which led to one of our external apps being offline for a bit and it showed us that we have to work on our alerting a bit.

I had never participated in doing a postmortem before. I know that some teams/people had already done some for past incidents, but we hadn't really created a process for doing them and now we are creating a process and I have now participated in a postmortem for the first time.

We are using this [template](https://github.com/dastergon/postmortem-templates/blob/master/templates/postmortem-template-srebook.md) right now and we have filled it during a meeting. For today's postmortem that meant creating a timeline first with everyone involved explaining what they did when and then we filled in the rest of the template. The timeline thing was very tedious though and we agreed on doing this asynchronously before the actual postmortem meeting next time.

We have identified two action items, one relating to the root cause of the problem and one for improving our monitoring and alerting across teams. The postmortem is now a pull request in our postmortem repository so people who have not participated in the meeting can review it, ask questions or add to the timeline.

I think there is room for improvement on how we are using these postmortems, but it's a good start to have all things relating to bigger incidents in one place and work on improving our systems collaboratively.
