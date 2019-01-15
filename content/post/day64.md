---
title: "Day64: Ich kann (noch) nix"
date: 2019-01-15T10:31:08+01:00
tags: ["nix"]
draft: false
---

The title means that I devoted a big part of my day reading about nix, but it was a huge intro and now I need to put my thoughts in an order.

Today I tried something I had in mind for a while: Learning in Pomodoros. It is a technique found in most articles and books about productivity at work, reducing distractions and efficient learning. I was afraid that this kind of strict splitting of my time in intervals would have a negative effect on my "multitasking" personality, but as I recently discovered that I was living a lie ( [more info](https://www.apa.org/research/action/multitask.aspx) ), I gave it try. I did 3 pomodoros in the morning ( 25min is recommended but I did 20min) and I am amazed. It was challenging to go against my bad habit of mixing the things I want to focus on, but I was surprisingly rewarded with a better learning speed. I will definitely continue splitting my time more wisely this week.

What is nix?  
---------  
Nix refers to a couple of things :   
--- _Nix: The pure functional package manager_.   
It works completely isolated from other package managers and will not modify any of your globals.   
--- _NixOs_, a linux distribution in which I will look tomorrow. You can deploy your NixOs machine with NixOps.  
--- _Nix programming language_, which defines the nix packages.

It is big and amazing, but the community looks small - still, I found the documentation very good for a newcomer; started with an intro and got you right away into hello-word action. You create a virtual environment where your packages are stored in the _Nix store_ with their unique subdirectory and a hashed ID. Your packages are never destroyed by new changes; instead, every changed version is handled as a new package.


Why?
------  
* For teams that need an identical development environment is a great option, because you can reproduce this setup again and again.
* The whole dependency tree is stored under a singe hash, so you can version control it, which means that you can also do rollbacks. Great!
* It got my attention, that Nix has "atomic upgrades". It can happen that during an istallation a sudden failure could be fatal or just leave a problematic system behind it. But not with Nix!  

No more dependency hell? Diamond problem of shared libraries solved? Seems like it.
I will confirm all my info above with a small hands-on tomorrow to make it a wrap.

[Song of the day](https://www.youtube.com/watch?v=vB67ddBhO1c)
