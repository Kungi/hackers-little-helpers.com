---
layout: post
title: "save *and* read a commands output"
author: cherti
draft-created-date: "2015-03-21 16:03:59 +0100"
---

Ever wanted to save a long-running commands output, but were annoyed that you then have to open the file to see what's going on and how far the command has run?

Something like
~~~
ls -lh > myfile.txt
~~~

The solution is: `tee`
With it you can pipe the output of a command into a file as well as keeping it on stdout (for reading or for piping it further):

~~~
ls -lh | tee myfile.txt
~~~

In both commands you will end up with the output in the file `myfile.txt`, but in the latter case, you also see the output in your terminal.

You also can append to a file:


~~~
ls -lh >> myfile.txt
~~~
corresponds to
~~~
ls -lh | tee -a myfile.txt
~~~

Another usecase I was told of is

~~~
curl http://download.grml.org/grml96-full_2014.11.iso | tee /tmp/grml.iso > /dev/sdb
~~~

You can think about what that does yourself. ;)
