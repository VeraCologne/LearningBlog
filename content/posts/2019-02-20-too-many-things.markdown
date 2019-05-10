---
layout: post
title:  "The One With Too Many Things To Remember"
date:   2019-02-20 14:13:47 +0100
tags: 
- architecture
---

We have `Shared` Modules in our applications. Right now they just get copied around, we want to put them into a library or something like that later. For both copying and library it's important that no app-specific stuff is inside these modules. And I keep forgetting this.

Today I wanted to add another option to a function that creates a metadata struct for our external events from data it gets from our EventStore events. One value needs to be whatever is in the EventStore event or our just our domain name. The `map_metadata` function was called in our event publisher and after that, this one value was changed, inside the publisher module, to the generic domain name value (because that's how this event used to be published, because for this specific event, the value from the event store would always be nil).

I thought "Great, there is this `map_metadata` function that already uses the correct value, so I'll just add the fallback there as well!" Nope. No app-specific stuff in `Shared` modules. I have now added a sticky note to my monitor saying exactly that. But I am pretty sure this is not the only thing that I tend to forget quite often in the heat of things. And I don't have that much space at the bottom of my screens.

There must be a better way for thinly-stretched junior developers to remember stuff like that instead of getting lost in problem solving, right?
