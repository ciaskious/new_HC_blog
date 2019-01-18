---
title: "Day66&67: From Nix to Docker and thoughts"
date: 2019-01-18T16:10:36+01:00
draft: true
tags: ["nix", "docker"]
---

Today I devoted some more time into the nix pills. They are part of the documentation; small digestible chunks (pills) devoted to each part of nix in order to help you dig deeper. So, some more notes after taking my pills:  

--- we use 'derives from' instead of 'depends on'
--- The .drv files  
They are called _derivations_. They are written in the Nix language and nixpkgs

symlinks not the usual usr blah blah dirs

and they lead us to
nix profiles.

nix shell is a temporal env. Here you can work with your reproducible env
nix env
