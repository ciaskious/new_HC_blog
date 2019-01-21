---
title: "Day66&67: From Nix to Docker and thoughts"
date: 2019-01-18T16:10:36+01:00
draft: true
tags: ["nix", "docker"]
---

Yesterday, I was devoting some more time into the nix pills until I wasn't. A new pairing session came up with [Wolfram](https://twitter.com/wolframkriesing) and if only I knew how crazy this ride would end up being. Long story short, we ended up testing Docker containers with TDD...

I will start my post with yesterday's Nix pills. They are part of the documentation; small digestible chunks (pills) devoted to each part of nix in order to help you dig deeper. So, some more some wrap-up notes after taking my pills, on theory that's hidden in every NIXer's (definitely non-functional) brain :  

--- we use _'derives from'_   instead of   _'depends on'_ .  
--- Deriviations (which take some time to really get them) use nix expressions in order to build packages from a set of attributes... so, we also  have `_derivations_` instead of `_packages_` .  
--- The .drv files: They describe how to build _derivations_ in simple words (because nix expressions are a little fuzzy), but they won't be build them until we tell nix to do so.  
--- It uses `symlinks` (aka not the usual usr blah blah directories)   
--- `Nix profiles` are the different user environments with the already installed packages. Every time you create a new user environment, you get a new generation/version of your profile. With `_nix-env_` you can manage all the above.  
Note: the files in the profile are just symlinks. All the real packages are installed  in `/nix/store`.  
--- `Nix shell` is a temporal env. Here you can work with your reproducible env aaaaand this is when my train of thought took off.  

Point of the pairing session, was to create a seperate development environment, so that production code is not in danger. But for this job we are creating a docker container instead.  

[ Starting with a mysql database I suddenly realised that I haven't needed a single database since University. I got the [Seven databases in 7 weeks](https://www.amazon.com/Seven-Databases-Weeks-Modern-Movement/dp/1680502530/ref=sr_1_1_cpbg?ie=UTF8&qid=1544795720&sr=8-1&keywords=Seven+Databases+in+Seven+Weeks) book a couple of weeks ago; it's time to get started with it and play around with this topic before my apprenticeship is over. ]   
--- New learning: The storage engine. MySQL has InnoDB, which since 2010 has replaced MyISAM. It is based on ISAM but has brought more features, like commit, rollback and recovery to protect user data. It also implements transactions, foreign keys and relationship constraints.  

After our dockerfile  with the mysql base image and started working around it.    
A question came up in my head? And the cool thing is, I am not the only one with this question: If I can reproduce my environment with docker, then why the heck should I use Nix? Well, here is one highlight that I confirmed myself.  

* If you delete or add a package in your Dockerfile you have to rebuild your image. Apart from that, you install your packages from  scratch and not only affects your speed, but also you cannot always be sure for the outcome of the installations because the shell commands depend on outside sources.

Nix and Docker are 2 different tools. Nix is an amazing package manager. Docker is a life-changing containerization tool which helps you ship and scale your app, but mostly used to reproduce builds; something that Nix does extremely well as a functional package manager. 

[Song of the day](https://www.youtube.com/watch?v=VJ_dOwxJv-w)
