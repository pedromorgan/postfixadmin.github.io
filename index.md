---
root: .
title: Welcome to PostfixAdmin
layout: pfa
---

**PostfixAdmin** is php powered web interface to configure and manage 
a [Postfix](http://www.postfix.org/) email server.
 
<div class="alert alert-warning" role="alert">
  <strong>Warning!</strong> PostfixAdmin is intended for new installs with its database schema which postfix, dovecot etc use.
</div>

![Alt text](https://g.gravizo.com/svg?
  digraph G {
    postfixadmin  [label="PostfixAdmin", style=filled, fillcolor=orange];
    database [shape=box, style=filled, fillcolor=pink];
    postfix  [label="Postfix", style=filled, fillcolor=lightgreen];
    dovecot  [style=filled, fillcolor=lightgreen];
    autoreply  [style=filled, fillcolor=lightgreen];
    postfix -> database [label="domains, users, aliases", fontsize=10];
    dovecot -> database [label="mailbox", fontsize=10];
    autoreply -> database [label="on holiday?", fontsize=10];
    database -> postfixadmin [dir=both];
  }
)

## Features

- manage mailboxes, virtual domains and aliases
- vacation/out-of-office messages
- alias domains (forwarding one domain to another with recipient validation)
- users can manage their own mailbox (change alias, password and vacation message)
- quota support for single mailboxes and total quota of a domain
- display used quota
- fetchmail integration
- commandline client postfixadmin-cli for those who don't want to click around in a web interface ;-)
- Squirrelmail plugin

## Overview

**PostfixAdmin** has a concept of a 
- "global" administrator (think 'root' superuser) 
- domain administrators
- regular users

When PostfixAdmin is initially installed, the `setup.php` url
- creates the global administrators account
- Using this global account, one can also create 
  domain administrators who are 
  limited to making changes within the domains you specify for them.

Needless to say, as a global administrator, you can do all kinds of bad 
things such as deleting domains and stopping delivery of mail to a 
particular mailbox. So take care, and if unsure take semi-regular backups.

If a login is not an administrator i.e. 'regular' user who just has 
a mailbox on the server, then the user will only see functionality to 
modify their own account - e.g. change password, edit forward records and specify 
whether on vacation (out of office) etc.


<iframe width="560" height="315" src="https://www.youtube.com/embed/UWh3Jvj6MC4" frameborder="0" allowfullscreen></iframe>
