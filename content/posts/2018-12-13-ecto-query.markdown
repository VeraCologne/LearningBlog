---
layout: post
title:  "The One With Ecto.Query"
date:   2018-12-13 16:43:47 +0100
tags: 
- elixir
- tools
---

I have finally been able to refactor my two long, very similar queries into smaller, composable ones by reading through the Queries chapter in [Programming Ecto](https://pragprog.com/book/wmecto/programming-ecto) today.

Turns out it is pretty easy and very obvious once I had understood the concept. Queries can be piped into another query and bindings from the first one are accessible in the second one in the order they were bound in the first query.

Other things I learned from this chapter:
- how to convert to a type when not using a Schema
- using `having` for aggregates

#### Things I don't know much about
- Databases and SQL. I will continue reading through Programming Ecto and see how far I can make it with my limited understanding of the underlying concepts. Once I'm done or stuck, I will find a way to improve my knowledge about databases and SQL.
