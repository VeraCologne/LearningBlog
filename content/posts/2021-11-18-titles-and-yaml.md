---
title: "The One With Titles and I18n"
date: 2021-11-18T18:10:53+01:00
tags:
- pragprogwrimo
- rails
---

I spent a good chunk of my morning wondering why I have forgotten how to use translation files in Rails with HTML tags and interpolation. I had a translation string like `"foo %{bar}</br>baz"` and the output was `foo bar_value</br>baz`. I thought that my string should be correct but I went looking around the app for other localisations. I didn't find one with both HTML tags and interpolation, though. So I looked into the I18n Rails API documentation and it still looked like I was doing everything right.

So I put my string into another localisation key and that looked like it worked. So where was the problem? I was using a tooltip with a title attribute and title attribute by default do not interpret HTML tags. Adding `html: true` to the tooltip fixed my problem. Such a tiny thing and such a long time spent running into the wrong direction.
