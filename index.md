---
root: .
title: PostfixAdmin home
layout: pfa

MAIN_TITLE: Welcome to Revel, the Web Framework for Go!
---

Postfix Admin is a web based interface to configure and manage a Postfix based email server for many users.
 
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


## Requirements

- Postfix (success has been reported with Exim!)
- MySQL or PostgreSQL or SQLite (>= 3.12)
- PHP
- And presumably a compatible IMAP/POP3 server (dovecot and courier seem to be the most popular)

