---
layout: post
title:  "The One With Ecto.Schema"
date:   2018-12-27 20:43:47 +0100
---

After all the eating and mindless conversation during the Christmas days, I decided today is a good day to get back into doing something useful, so I read the Schema chapter in [Programming Ecto](https://pragprog.com/book/wmecto/programming-ecto).

It did not provide me with lots of new information because I had kind of grasped the most important ideas of Ecto.Schema from the way we used it in our projects. But I learned how to use many-to-many associations with or without a join table Schema. And I learned that the reason you have to preload associations when you want to use them is that Ecto prevents you from accidentally doing N + 1 queries that way.

#### Things I don't know much about
- Database basics, again. Today specifically how queries are done from a database point of view. Because I think I kind of get the problem with lazy loading associations but I don't fully understand it.
