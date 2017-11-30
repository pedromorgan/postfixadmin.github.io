---
root: .
title: Welcome to PostfixAdmin
layout: pfa
---

**PostfixAdmin** is php powered web based interface to configure and manage 
a [Postfix](http://www.postfix.org/) based email server.
 

![Alt text](https://g.gravizo.com/svg?
  digraph G {
    postfixadmin  [label="PostfixAdmin", style=filled, fillcolor=pink];
    database [shape=box, style=filled, fillcolor=lightyellow];
    postfix  [label="Postfix", style=filled, fillcolor=lightgreen];
    dovecot  [style=filled, fillcolor=lightgreen];
    autoreply  [style=filled, fillcolor=lightgreen];
    postfix -> database [label="domains,\nusers,\naliases", fontsize=10];
    dovecot -> database [label="mailbox", fontsize=10];
    autoreply -> database [label="vacation", fontsize=10];
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

<div class="alert alert-warning" role="alert">
  <strong>Warning!</strong> PostfixAdmin is intended for new installs with its database schema which postfix, dovecot etc use.
</div>

<iframe width="560" height="315" src="https://www.youtube.com/embed/UWh3Jvj6MC4" frameborder="0" allowfullscreen></iframe>