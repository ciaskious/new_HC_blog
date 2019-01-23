---
title: "Day70: My own SeQueL"
date: 2019-01-23T15:39:03+01:00
tags: ["apprenticeship", "databases"]
draft: false
---

I am trying not to break blog posts' sequel for this week, so here is the day after my breakdown.  

Trying to see yesterday's mistake as part of a kata, today I have the chance to run again my container more carefully and get the job done much better.  

Before doing that, I touched a book I found here on MySQL, which gave me the chills - I had a look on Database Design and then I left it aside forever.  

>Being an apprentice for all this time, switching topics that often, while trying to dig deeper, sometimes drives you nuts. But what I am learning is structuring my day and making it effective.   

I have to confess that my approach to new things becomes slowly more targeted. Stuff that took me 1 week to understand and start implementing, now take 3 days; I never thought that explaining them out loud to my peers daily just for fun, would help me realise what I am doing. The first days I was losing my breath and made myself uncomfortable, now I do it on purpose - sharing is caring...  

Improvements:  

* I changed my docker run command a little bit. When the MySQL container starts running, you get stuck in the terminal, unable to do anything (unless you change tabs of course). Detaching the container(running in the background), works like a charm: `docker run --detach --name=mysql-example mysql-image`  

* Got some resources from my mentor on SQL. Koans, of which I have never heard before, are a kata-like way to learn new things. These SQL koans [here](https://sqlkoans.com/) made my day. It took me some extra energy to focus on some of them, but in the end I got all the basics I was missing yesterday. Plus points: ran the whole process on tmux - finally felt so much faster.  

* Changed my Dockerfile  

```
FROM mysql:8.0.14

ENV MYSQL_ALLOW_EMPTY_PASSWORD='yes'  
VOLUME ["/databases"]  
WORKDIR /databases    
```    
Instead of having a long run command in my scripts, I prefer to add my variables clearly in the Dockerfile for now. This kept me sane for today: I have a filesystem where I can take files from the host and dump in there my Database in case I do changes in the future.  

[Song of the day](https://www.youtube.com/watch?v=8YdQBkxf4kU)
