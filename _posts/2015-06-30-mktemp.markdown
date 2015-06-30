---
layout: post
title: "mktemp - the easy way to get temporary files (and dirs)"
author: cherti
categories: tool
---

Ever spontaneously needed a temporary file? Your playground is overflowing with files named `a`, `aa`, `aaaa`?

Well, just take `mktemp`! Once called, it returns the path to a guaranteed empty file below `/tmp` that can be used for whatever you need it for.

But it doesn't stop there. Ever wanted to play around with something and did not want to make a mess in your working-directory?
Just use `mktemp -d` and you get the path to a directory below `/tmp` that will be created on the fly and is guaranteed to not exist before.

Or use `cd $(mktemp -d)` and you will immediately end up in one of those empty directories on your shell.

Happy playing around in there. ;)
