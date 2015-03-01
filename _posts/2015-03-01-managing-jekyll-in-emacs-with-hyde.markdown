---
layout: post
title: "Managing jekyll in emacs with hyde.el"
author: Andreas 'Kungi' Klein
draft-created-date: "2015-01-23 10:49:44 +0100"
categories: emacs
---
[Hyde][] is a quite minimal jekyll frontend for emacs. It depends on
your jekyll files being stored in a git repository (what you should do
anyway). See the following picture for an example of the user interface
of this blog.

![Hyde user interface](/images/hyde-example.png){: .center-image }

For hyde to work you have to craete a .hyle.el file in your blogs
main directory.

This blog uses the following:

~~~
(setq hyde-home "~/blogs/hackers-little-helpers.com"
      hyde/git/remote-branch "gh-pages")
~~~

[Hyde]: https://github.com/nibrahim/Hyde
