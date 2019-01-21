---
title: "Day68: TDD for infrastructure (First Try)"
date: 2019-01-21T12:07:56+01:00
draft: false
tags: ["docker", "tdd"]
---
I haven't really finished my Friday's story considering TDD for infrastructure.
It is inspired by [this talk](https://github.com/sirech/talks/blob/master/2019-01-tw-tdd_containers.pdf) from Mario Fernandez.  

As a noob in Docker, all I have done with it while playing around:   
1) write the Dockerfile for my app  
2) build my image
3) oops something's wrong, let's go to step 1).  
If you successfully build your image 4) Run your container   
5) maybe it works, other back to 1).  

And sadly this is more or less what happens with containers in production as well... But what if you implement TDD to reassure that everytime you commit, your container is not broken?  

The tool used in the talk was Serverspeck and ruby, but in this post it is replaced with [goss](https://github.com/aelsabbahy/goss) - a YAML based testing tool. More specifically, with dgoss, which tests docker images. Maybe with less options than coding with Serverspeck. What is shown in the examples though, is just validation of the images. What we really want to see, is the tests driving us while writing the Dockerfile - the actual TDD part.  

Compared to Mario's talk, this dgoss approach takes some more thought and sweat. First of all, this whole testing scenario takes place in a running docker container. Starting from this, an image where dgoss is installed is required so that we can test the container that we will run in it. Sounds like Docker-in-Docker, which is so not recommended ( [more here](https://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/)) but the trick is this variable when running your container ` -v /var/run/docker.sock:/var/run/docker.sock`. This is the way of using the host machine's socket, so that you create the illusion of "siblings" between them and not been seen as Docker-IN-Docker.  
Setting up and running the development container is now solved, next step is to begin the first test on the image and potentially running container I want to create.  

This is the tricky part I am struggling for now. Goss is supposed to be a server validation tool, and in our case its whole documentation is based on creating your image and then, either by using some commands for autogeneration, or by writing your own yaml file, to test-run your container with dgoss instead of docker.  

 Its philosophy makes it hard to use the edit commands provided for TDD. You have to write the yaml yourself, as using the edit command for yaml generation starts a container. This is probably a bad start, as I haven't even tested my base image yet. I am supposed to have an empty Dockerfile and be driven there by tests, which with Serverspeck and code seems much more doable. For now I've tried and failed. It might be that it just works differently... Tomorrow I will put more effort into it.  

[Song of the day](https://www.youtube.com/watch?v=MuBEJ4nS5Lc)
