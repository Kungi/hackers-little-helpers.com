---
layout: post
title: "Timestamps and timeranges in org-mode"
author: Andreas 'Kungi' Klein
categories: emacs org-mode
---

In org-mode there are two kinds of timestamps, active and inactive.  This
is an inactive timestamp `[2015-01-29 Thu]` and this is an active one
`<2015-01-29 Thu>`. Active timestamps can be clicked on and link to the agenda.

You can create timestamps with the following keys:

* `C-c .` - active
* `C-c !` - inactive

Timestamps can not only represent dates but also times like this
`[2015-01-29 Thu 18:01]`.  You can create a timestamp including a time by using
the universal argument `C-u` like this `C-u C-c !`.

By moving the point (Emacs speak for cursor) on a timestamp including a time and
adding another timestamp on top of it you create a time range
`[2015-01-29 Thu 18:03]--[2015-02-18 Wed 19:30]`.  When an active timerange is
clicked on it shows the agenda for this range.

Timeranges are also used when clocking time in org-mode. When used in a clocking
context they can even be evaluated to show the hours and minutes they span. Just
press `C-c C-c` on the timerange to get the output `=> hours:minutes`.

See the following example for this:
`CLOCK: <2015-01-29 Thu 18:05>--[2015-01-29 Thu 19:05] =>  1:00`







