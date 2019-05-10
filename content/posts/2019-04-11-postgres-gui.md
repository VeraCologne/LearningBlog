---
layout: post
title:  "The One With a Postgres GUI"
date:   2019-04-11 08:55:00 +0200
---

Loosely related to my pledge to myself not to hurry things anymore, I have taken some time to look into Postgres GUIs. I have never had one, always queried the database from the command line but I do see that it becomes a bit difficult with longer queries and I just don't understand the structure of all the events stuff (especially when using Commanded) so I've always pushed questions about this to someone else.

One of my colleagues uses Navicat and upon searching on Google, I have also come across TablePlus. I did a quick comparison and like TablePlus a bit better. I can set up a connection with a database URL and I can get warnings when I try to update something. This might work with Navicat as well, but I couldn't find it immediately. Also, in the unlikely case of us using something other than Postgres at some point, TablePlus' normal license allows connections to multiple databases, Navicat's similarly-priced products only support one type of database.

Other things I'm working on: Switching from Jekyll/Github Pages to Hugo/Netlify. I'm struggling with the Victor Hugo boilerplate in connection with a theme and have asked for help. We'll see ...
