---
layout: post
title:  "The One with Epics and User Stories"
date:   2019-01-28 20:13:47 +0100
tags: 
- apprenticeship
---

I started writing epics for my dashboard project, along with some mockups and there are some things I noticed:

I have an epic for a Happiness Index metric. We do a Happiness Index in our retrospectives with scroes from 1–5 for "How satisfied are you with your role at Studitemps?" and "How satisfied are you with Studitemps as a company?". The averages for each team have so far been tracked on a piece of paper or in a Google sheet. The idea for the dashboard is to let someone enter the different values into this application which then calculates the averages and displays them. There are several user stories I can derive from that:
- ability to add some values and get the average
- ability to add values for both metrics
- ability to add values for different teams
- save and display metrics for a team
- display metrics for several teams
- calculate a trend line for the metrics
- calculate averages across teams
- ability to toggle which metrics are shown (team, one of the questions, ...)
This epic also serves a bit as an example for other metrics where users have to actually enter some data.

The other epic I have right now is about configuring the dashboard. A user should be able to decide which of the available metrics are useful for them and which they want to see. Stories I saw from my initial draft of the epic:
- let a user choose the metrics they want to see
- save a user's choice and show it to them whey they log in again
- provide a filter for metrics (if there are lots of them, it might be useful to filter them by category)

When we talked about this in our review/planning session today, we came up with some others:
- pre-select metrics based on a user's role in the company
- let a user choose how often they want their metrics to update
Still, this is a lot smaller than the other one.

The other things I have planned were difficult for me to put into user stories or epics. Is "one specific metric should be shown" really worth writing a story for, let alone an epic? They are all kind of similar and I don't really know what the user's goal would be for a lot of them.

In our meeting we talked about the idea to see me as the user who wants to achieve a goal from this dashboard: I want to learn how to implement different things. So I could maybe write user stories from my point of view? I will have to think about this a bit more. Next steps:
- Split the existing two epics into user stories. Those which have to be implemented for the dashboard to make any sense, will be written out further and probably have some mockups attached to them. Those who are just icing on the cake will probably only get a rough explanation.
- Choose 2–4 more metrics I could track in addition to the Happiness Index as a starting point. Criteria for choosing the right ones:
1. They should come from different data sources so I can learn more.
2. They have to provide some value to the company so people could actually use this thing.
