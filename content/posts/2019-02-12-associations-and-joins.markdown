---
layout: post
title:  "The One with Associations and Joins"
date:   2019-02-12 17:13:47 +0100
tags: 
  - elixir
  - tools
---

Another day, another database problem. What I did with my upserts yesterday worked, but the query to show this to the user was less than perfect. It was actually pretty bad and I knew it, but after overcoming several points of "What am I doing here? I'm never going to be able to get this done!" yesterday I decided that was a good problem to not try to solve on my own.

I showed it to a coworker who (friendly) grunted "yeah, that's not a good idea" and then suggested that I connect the two domain models that are shown to the user there with an association. At first it looked like it worked. I had to figure out how to use a string as a foreign key, but that wasn't too difficult. My view was still showing what it was supposed to show, but some other tests broke. We again looked at this together and realised that it wasn't good to change the model because it would change the write part and not only the read part (which is what I needed) and instead join the two models in the view query.

Through a test that did not insert a record for one of the models beforehand, I realised that my query wasn't working if it didn't find a record to join. The view needs to work for this though, and I had actually implemented it to work correctly, but only if the query returned nil for this record. I knew that the solution had something to do with a left join but I didn't come up with anything that was working. I decided to first write some more tests for different cases and go from there.

After lots of trial and error and tons of swearing and a few tears (luckily I was at home), I was finally able to implement it:
```
from(
  a in FirstModel,
  left_join: b in SecondModel,
  where: is_nil(b) or b.id == a.second_model_id
)
```
I'm writing this down here in hopes of never forgetting it again. I had actually struggled with a very similar problem before, shed some tears then as well, and felt very stupid when I saw my coworker's solution.

#### Things I don't know much about
- How to not get upset when I can't find a solution to my problem. Although it has gotten a lot better. I *am* able to get out of my head and try different ways now, and I *do* often find a solution. It's just still really draining, working like this.
- How to describe a problem in a way that someone who hasn't seen this code for a while understands what I am talking about. I find it very difficult to provide the right amount of information.
- How to describe my work here without using the actual concepts and code. I am pretty sure that some of what I have written does not make a lot of sense or is just plain wrong. But I am missing the words to correctly describe it.
- Databases. Still and again. But it is getting better.
