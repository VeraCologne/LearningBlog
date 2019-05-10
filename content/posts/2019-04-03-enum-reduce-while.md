---
layout: post
title:  "The One With Enum.reduce_while"
date:   2019-04-03 08:55:00 +0200
tags: 
  - elixir
  - tools
---

I have an irrational fear of reduce functions. I have needed to use `Enum.reduce()` a few times and it either did not work or I copied some code from somewhere else and managed to substitute what I needed.

Yesterday I needed to calculate days for a list of objects with a start and end date. But only for those starting this year and those starting less then 21 days after another object that counts. I asked our PO a few questions about the specifics and then looked at his answer and thought "Oh no. That's got to be some kind of reduce_while." I went back to an old project where we had used this for something a bit different, copied the code and started from there. It was quite a hassle to get all the objects in order for starting the reduce function (sort all objects, split them into this year's and future ones, compare the first future one to the last one from this year, continue in pairs until there's a break of 21 days) and it took me a long time, lots of shuffling code around and quite a few swear words but it worked eventually. And then I realised that I needed to test the cases where there are no objects this year or none in the future and that lead to some nasty if clauses, but I figured this out as well.

The code is ugly. I managed to split up the long-ass function into smaller chunks after taking a break for a few hours, but it's still rather messy. There is definitely one branch that I need to get rid of but I still can't figure out how. But I'm really proud that I managed to do it!
