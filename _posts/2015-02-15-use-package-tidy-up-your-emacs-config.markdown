---
layout: post
title: "Use use-package to tidy up your emacs config"
author: Andreas "Kungi" Klein
draft-created-date: "2015-01-29 19:48:17 +0100"
---
Many emacs configurations are an unorganized mess. [use-package][] helps with
organizing your config and keeps everything related to one package in one macro
call. It also prevents packages from being loaded when they are not available on
your system.

Take the command `(use-package foo)` as an example. The time it takes to load
`foo` is logged and it is only loaded when available. The loading of a package
can be deferred until it is used.

`use-package` provides many ways of triggering actions when a package is loaded.
Among those are `:init`, `:config` and `:bind`.

- `:init` is always run, even if the package is not loaded.
- `:config` is only run when the package is loaded successfully.
- `:bind` binds keys.

See the following example:

~~~
(use-package haskell-mode
  :commands haskell-mode
  :init
  (add-to-list 'auto-mode-alist '("\\.l?hs$" . haskell-mode))
  :config
  (progn
    (use-package inf-haskell)
    (use-package hs-lint)))
~~~

`:commands` creates an autoload for the `haskell-mode` command and derfers loading
until this command is called. Init sets up the usage of `haskell-mode` for each
`.hs` file. When a haskell file is opened the autoload triggers and and the
`:config` key is executed. This loads some more packages.

[use-package]: https://github.com/jwiegley/use-package
