---
layout: post
title: "A small trick for copy-paste"
author: koebi
categories: tool
---

Every once in a while, i stumble upon the problem of wanting to paste output of
any command-line-tool somewhere else, being it a complicated path I don't want
to type again, wanting to cat a quite huge file and pasting it somewhere or for
any other reason you can come up with.

Of course, you could do it ("copying the linux way") using the middle mouse
button, but sometimes this gets quite complicated, or your output is too long
for your terminal to scroll through, or anything else.

As a solution to that, I recently discovered the beautiful xclip-tool.
It works like this:

~~~
	koebi@term1 $ cd very/complicated/path
	koebi@term1 $ pwd | xclip -i

	koebi@term2 $ <middle mousebutton><enter>
~~~
or

~~~
     koebi@term1 $ cat mailtext.txt | xclip -i
~~~

or else. Quite convenient :))

- - -
Für die deutschsprachige Welt: Dieser Post existiert auch auf deutsch unter
[http://blog.ezelo.de/simple_pasting/](blog.ezelo.de), meinem eigenen Blog, auf
dem ich so poste, was mir unter die Finger kommt. Erwartet nicht zu viel Inhalt
;)

