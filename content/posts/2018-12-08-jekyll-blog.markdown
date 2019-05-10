---
layout: post
title:  "The One With the Jekyll Blog"
date:   2018-12-08 19:43:47 +0100
tags: 
- blog
---

This is my second attempt at publishing this blog. I have set it up with Jekyll, which was fairly easy (after I had updated my ancient ruby version), changed a tiny bit in the config file and then wrote a blog post in markdown. So far so good. 

When I tried to publish it to GitHub Pages, it just didn't work at all. At first there was nothing, then I somehow managed to get an unstyled page with broken links up, then it was back to nothing and GitHub somehow refused to change the repository back to private. 

So this is my second attempt. It looks like my problems were coming from me using a project folder and not my main GitHub site as a source, so all the links (including those to stylesheets) were broken. I have now set up a baseurl in my config file, so fingers crossed it will work this time.