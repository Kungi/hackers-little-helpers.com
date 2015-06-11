---
layout: post
title: "offlineimap - sync imap mailboxes to your harddrive"
author: Andreas 'Kungi' Klein
draft-created-date: "2015-03-21 16:05:34 +0100"
---

For almost all terminal based mail readers like mutt or pine access to a maildir
structure is necessary. But most of the time mail exists on an IMAP server
possibly one where we do not have a shell account (like googlemail).

So how can one IMAP with mutt? One solution to this problem is offlineimap.
[Offlineimap][] syncs an IMAP account into a local Maildir. For a configuration
example see the minimal offlineimaprc example from the [Archlinux Wiki][].

    # ~/.offlineimaprc

    [general]
    # List of accounts to be synced, separated by a comma.
    accounts = main
    
    [Account main]
    # Identifier for the local repository; e.g. the maildir to be synced via IMAP.
    localrepository = main-local
    # Identifier for the remote repository; i.e. the actual IMAP, usually non-local.
    remoterepository = main-remote
    # Status cache. Default is plain, which eventually becomes huge and slow.
    status_backend = sqlite
    
    [Repository main-local]
    # Currently, offlineimap only supports maildir and IMAP for local repositories.
    type = Maildir
    # Where should the mail be placed?
    localfolders = ~/Maildir
    
    [Repository main-remote]
    # Remote repos can be IMAP or Gmail, the latter being a preconfigured IMAP.
    type = IMAP
    remotehost = host.domain.tld
    remoteuser = username

Offlineimap can do much more than only sync IMAP to Maildir and back. I
regularly use it to make backups and also installed a postsynchook which runs my
mail indexer `mu` after every sync.

[Archlinux Wiki]: https://wiki.archlinux.org/index.php/OfflineIMAP
[Offlineimap]: http://offlineimap.org/
