---
title: "The One With Phoenix Conn.Test"
date: 2019-06-05T19:13:53+02:00
tags: 
- apprenticeship
- phoenix
- elixir
- tools
---

In our review meeting on Monday, we finally looked over my first bit of code for my Happiness Dashboard project. We talked about splitting the controller based on use cases vs. having one controller for the Happiness Index with actions for the things to do. We decided on using just one controller (and only one template actually) because this is so small and tiny. If at some point I decide to do more on this, I can still split it up better. 

We also talked about how to test this. As mentioned before, I struggle with writing tests from the outside in. Additionally, I don't want to add a feature testing tool at the moment. I feel like this is a huge overhead with almost no value. In our projects at work, we do a pared-down version of Specification by Example, writing Cucumber scenarios and implementing them using Wallaby to test user interactions. And even for our real projects, I struggle to see the big benefit in doing it like that. It is an incredibly painful process getting the specification to a point where everyone agrees on them AND the steps are easy to test. I haven't really understood Wallaby so far and I almost always give up at some point when my UI assertions don't work. Why is the text element not there? I can clearly see it in the screenshot that was taken one line above the assertion. Why does this function not wait for the element to be loaded, when it should do that according to the documentation? 

I like clicking. I know I am not supposed to say that as a real programmer, but I just do. I know that from the point of regression testing, an end-to-end automated test is great, but when I am writing the implementation? Please just let me click and see what's going on without pushing my `take_and_show_screenshot` function through 100 lines of code. My mentor told me to do just that then, and continue until the UI does not give me enough feedback to see what's not working. And then go a layer deeper, work on that test until it does not give me enough feedback and then go on. 

I had some validations to implement that I used to try this with. I have a form with two input fields (for satisfaction with role and company) that take a list of integers, saves these list and then shows the averages for both inputs. In my controller, the param string from the post request is transformed into a list of integers by splitting on the commas and then transforming these individual strings to integers. When I put in something else then an integer, it broke with an argument error for Erlang's `binary_to_integer` function. I wanted to instead show the user a flash message telling them to only put in a list of integers. 

I looked around for a way to test this as easily as possible and found `Phoenix.ConnTest`. With this, I can build a conn object and call the `post` action with a letter instead of an integer list and then use `get_flash` to see what's in the current flash storage and if it's the error message I was expecting. 

Inside my controller, I have two calls to an `to_integer_list` function and the call to my model to add these. I switched from just calling them and then redirecting with a success message to wrapping them in a `with` statement that checks if some form of list came back from the two calls to the internal function and an `{:ok, happiness_index}` tuple from inserting these. Inside the `to_integer_list` function, I `try` to transform the input into an integer list and `rescue` an argument error by giving back an error message So the `else` case from my with statement puts this error message into an error flash message. 

I know this is hacky. While googling how to use `try/rescue` I read that Elixir developers shouldn't do that. And this might be a validation that belongs inside the model (or is that not a domain thing but just handling user stupidity?). And I still need to validate that the integers can only be 1–5 and both lists need the same amount of elements. But at least I have a test now. Two, actually. One that posts characters instead of integers and one that does not comma-separate the integers. Oh wait, three. The happy path! And I learned a teeny tiny bit about ConnTest (although I'm not sure I'm using it in a sensible way).

I don't know how to go inside from there now, though. That's probably a topic for next week's session.