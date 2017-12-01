---
title: Postfix
name: postfix
layout: setup
---

Postfix Config


The **Postfix** installation will support either MySQL or Postgres lookup tables.

This can be verifed  with the command

```bash
postconf -m
```

# TODO the rest

Where you chose to store the .cf files doesn't really matter, but they will
have database passwords stored in plain text so they should be readable only
by user postfix, or in a directory only accessible to user postfix.

This isn't necessarily all you need to do to Postfix to get up and
running.  Also, additional changes are needed for the vacation
autoreply features.

# Contents of the files

These are examples only, you will likely have to and want to make some
customizations.  You will also want to consider the config.inc.php
settings for domain_path and domain_in_mailbox.  These examples
use values of domain_path=YES and domain_in_mailbox=NO

You can create these files (with your values for user, password, hosts and
dbname) automatically by executing this file (sh POSTFIX_CONF.txt).
Please note that the generated files are for use with MySQL. 

If you are using PostgreSQL, you'll need to do some changes to the queries:
- PostgreSQL uses a different implementation for boolean values, which means 
  you'll need to change  active='1'  to  active='t'  in all queries
- PostgreSQL does not have a concat() function, instead use e.g. 
  .... alias.address = '%u' || '@' || alias_domain.target_domain AND ....