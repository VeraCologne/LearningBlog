---
layout: post
title:  "The One where We Rename Things"
date:   2019-01-16 21:13:47 +0100
tags: 
- architecture
---

We recently discovered a naming problem in one of our applications where we calculate costs for cost units. Up until now, the data needed for the calculations was set for these cost units, but this does not actually make a lot of sense. The data comes from an and there are many other things that factor into the calculations for the cost unit.

We realised this when we started implementing a form for users to actually set this data. It just didn't feel right. When we talked about this, we first questioned whether we had cut our boundaries wrong. Since the order and the cost unit have the same identifier, it looked like we were talking about having an entity with two different names in one bounded context. But in reality, these are two different entities. An order may *become* a cost unit (with costs that *relate* to the order data and other input), but it doesn't have to and this transformation is actually the very thing our application does.

Today we started renaming everything that is in fact related to the order and not the cost unit. I did not think it would be that time consuming because I totally forgot that it's more difficult to change *some* references instead of all. And I got completely lost in the outer layers of our application: It's easy inside the domain, where some entities reference an order id. But in outer layers, sometimes it's the order, sometimes the id and sometimes even the shorter number (to show users for easier referencing). And I once again discovered that German is weird. A cost unit is "Kostenträger", multiple cost units are "Kostenträger". An order is "Auftrag", multiple orders are "Aufträge". Be careful when you want to rename these.

#### Things I don't know much about
- Phoenix. I'm pretty sure I had this before and it hasn't improved much. I got really confused in the router, controllers and templates.
- Raising a teenager. But I will learn this, somehow, soon. My son turned 13 today. How did that happen?
