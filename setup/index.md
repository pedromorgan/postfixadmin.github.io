---
title: Setup & Install Overview
layout: setup
---



## Requirements

- Postfix 2.0 or higher
  - success has been reported with Exim!
- Apache 1.3.27 / Lighttpd 1.3.15 or higher, nginx+php-fpm
- PHP 5.1.2 or higher
- Databases:
  - MySQL 3.23 or higher (5.x recommended)
  - MariaDB (considered as MySQL 5.x or greater )
  - PostgreSQL 7.4 or higher
  - SQLite 3.12 or higher (not recommended for production)
- IMAP/POP3
  - A compatible server such as dovecot or courier which are the most popular

## Target Machine

- it is assumed that there is `root` access to the target machine for installation
- a database is required to store data of domains, mailboxes users etc
  - this is the "PostfixAdmin" flavoured database
- PostfixAdmin website
 - the php application will setup and create the database
 - create a default domain etc
- Postfix
 - postfix will need to be configured to use the database
 - also postfix will need to be configured for vacation and alike
 - postfix configuration is not easy
 
 