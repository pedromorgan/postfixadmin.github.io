---
title: config.local.php
layout: setup
---

## PostfixAdmin config

There are two important files:
- `config.inc.php` which is the "default" configuration, updated by the postfixadmin team
- `config.local.php` which is the customised config for the machine setup

Check the `config.inc.php` file. There you can specify settings that are relevant to your setup.

Comparing config.inc.php with your previous using "diff" might save you some time.

You can use a config.local.php file to contain your local settings. 
These will override any defined in config.inc.php - and save some time when upgrading to a new version of PostfixAdmin ;-)