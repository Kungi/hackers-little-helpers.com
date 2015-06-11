---
layout: post
title: "ack und ag - searching source code the fast way"
author: cherti
categories: tool
---

Who doesn't know that. There is some source code and one wants to find out where one special function is called, because one has to fix this function and wants to determine the impact.
The solution for that might be abusing `grep` with the recursive-flag, but that is sooooo meh.

The actual solution for that problem is using `ack`.
`ack` is a little perl script that basically does the same as grep. The one of the interesting differences (but certainly not the only one) is: it goes recursively by default by, at the same time, omitting binary data and version-control-specific files (like everything below `.git/`).

And in case you find it slow: you are not the first one: just use `ag`, which provides the same functionality, but is implemented from scratch in C (to make things fast).

Searching source – the fun way: ack (or ag, the silver searcher) at your service.
