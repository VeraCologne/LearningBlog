---
layout: post
title:  "The One Where I Start the Dashboard"
date:   2019-05-02 10:55:00 +0200
tags: 
- apprenticeship
---

I am jumping in. I feel a bit nervous because I just have never done this. I know, a programmer who has never written their own application, it's weird. But hey, better later than never, right? This is what I have done so far: 

- Ran mix phx.new to create a new phoenix application
- Thought about the first domain model: the Happiness Index we gather in our department denotes a team member's happiness with their current role and with the company as an employer. Is that 2 models or one? I am going to start with one and see if that makes sense. If not, I can always go back and fine-tune my design.
- Figured out how to set up testing. Since I have started programming in this team, there has always been a working application to either implement things in or use to copy for setting up a new application. Turns out I am not sure how to use ExUnit, because we set up our own test cases that build on ExUnit's test cases. Apparently I can use ExUnit.Case
- Freaked out about what to do now. I remembered doing a Udemy tutorial on Elixir and Phoenix almost 2 years ago, so I looked into [the code for it](https://github.com/StephenGrider/ElixirCode). It has the model in the Web section, which I find confusing, and it uses some kind of model from `web.ex`, mine doesn't have that. Then I googled around and found the task `mix phoenix.new.model` in the official Phoenix documentation, but I can't run it, it can't be found. So I guess I have to do it on my own? 
- Written a schema and migration for the model. So far it consists of 2 arrays with integers.
- Decided I have no idea where to go from here and that I really think I should start from the outside, so I should probably commit my model and then start figuring out how to add a page and entries and things like that. 
- Realised I had forgotten to set this up as a git repository and did that. 

And then I decided that was enough for a day (in which I did tons of other stuff as well). I don't think this is going too well so far, but maybe inspiration will strike me in the next days.