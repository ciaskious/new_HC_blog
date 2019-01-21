---
title: "Day68: TDD for infrastructure"
date: 2019-01-21T12:07:56+01:00
draft: true
tags: ["docker", "tdd"]
---
I didn't really finished my Friday's story considering TDD for infrastructure.
We got inspired by [this talk](https://github.com/sirech/talks/blob/master/2019-01-tw-tdd_containers.pdf) from Mario Fernandez.  

As a noob in Docker, all I have done with it while playing around:   
1) write the dockerfile for my app  
2) build my image
3) oops something's wrong, let's go to step 1).  
If you build your image 4) Run your container   
5) maybe it works, other back to 1).  

The tool used in the talk is Serverspeck, but in this post it is replaced with goss - a YAML based testing tool. More specifically, with dgoss which tests docker images. What is shown in the examples though, is just validation of the images. What we really want to see, is the tests driving us while writing the Dockerfile.  
