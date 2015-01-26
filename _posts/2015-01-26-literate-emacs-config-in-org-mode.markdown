---
layout: post
title: "A literate Emacs config in org-mode"
author: Andreas 'Kungi' Klein
categories: emacs org-mode
---
# Why would you want to do this?

It is the nature of an Emacs config to be always growing.  These configs can get
quite unreadable very fast. Org mode can help in this case. There are two main
reasons to write your Emacs config in org mode.

1. Folding and neatly organizing your Emacs config.
2. Annotating your Emacs config nicely in a literate style

# What you need

I keep everything Emacs related in `~/.dotfiles/emacs.d`. There I have two
config files.

- `emacs-local.org` - Here I keep some mac specific settings
- `emacs.org` - My complete Emacs config

Every time on Emacs startup I load these two files through org-babel.

```emacs-lisp
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; load neatly organized org file!
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; Local emacs config
(org-babel-load-file "~/.dotfiles/emacs.d/emacs-local.org")
(org-babel-load-file "~/.dotfiles/emacs.d/emacs.org")

```

Just keep your Emacs config in an org file. Here is an example from my `emacs.org`
(of course it looks much better in org mode).

```
* sticky-windows / dedicated
  #+begin_src emacs-lisp
    (require 'sticky-windows)
    (global-set-key (kbd "C-x 0") 'sticky-window-delete-window)
    (global-set-key (kbd "C-x 1") 'sticky-window-delete-other-windows)

    (require 'dedicated)
    (global-set-key (kbd "C-x 9") (lambda ()
                                    (interactive)
                                    (dedicated-mode 'toggle)))

  #+end_src
* no focus follows mouse
  #+begin_src emacs-lisp
  (setq mouse-autoselect-window nil)
  #+end_src
* restclient
  #+begin_src emacs-lisp
  (require 'restclient)
  #+end_src
```

You can easily insert the `#+begin_src emacs-lisp` by typing `<s` followed by
`TAB` in org-mode.
