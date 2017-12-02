---
title: Upgrade
layout: setup
---


It's recommend that you install Postfix Admin in a new folder and not
on-top of the old install!! (At the very least, make sure you have backups of 
the database and relevant filesystem!)

When upgrading **PostfixAdmin**, ensure you backup your database before
running `upgrade.php`.


## 1. Backup the Database

When you install from a previous version make sure you backup your database
first. There can be a lot of changes in the database structure eg:

- Replace postfixdb with your PostfixAdmin database's name
- `mysqldump -u root -p postfixdb > /tmp/postfixadmin-backup.sql`
- `pg_dump -ad -u postfix postfixdb > /tmp/postfixadmin-backup.sql`


## 2. Unarchive new PostfixAdmin

Make sure that you are in your WWW directory and then unarchive the
Postfix Admin archive :
```bash
tar -zxvf postfixadmin-X.X.tgz
```

## 3. Set permissions

Since the database password is stored in the `config.inc.php` it's a good idea
to have change the permissions for **PostfixAdmin**.

The last command below assumes your Apache is running with group "www-data"

```bash
cd /usr/local/www/postfixadmin
find -type f -print0 | xargs -0 chmod 640
find -type f -print0 | xargs -0 chown root:www-data
```


PostfixAdmin uses smarty templates, and "compiled" templates are written out to the `templates_c` directory
which needs to be writeable by the webserver. Example below is Apache  as user "www-data"

```bash
cd /usr/local/www/postfixadmin
mkdir templates_c && chmod 640 templates && chown -R www-data templates_c
```



4. Configure
------------

Check the config.inc.php file. There you can specify settings that are
relevant to your setup.

Comparing config.inc.php with your previous using "diff" might save you some
time.

You can use a config.local.php file to contain your local settings. 
These will override any defined in config.inc.php - and save some time when upgrading to a new version of PostfixAdmin ;-)

5. Run setup.php
----------------------------------------

Access setup.php through a web browser.

It will attempt to upgrade your database, and also allow you to create a superadmin user.
(In case the database upgrade fails, you can run setup.php?debug=1 to see the last executed query.)

From version 2.3, you need to specify a setup_password in config.inc.php - 
setup.php should guide you through this process. If you do not have a setup_password, type one
into the form, and setup.php will echo out the hashed value (which needs to go into config.inc.php).
The setup_password removes the requirement for you to delete setup.php, and also closes a security hole.

Since version 2.2 of Postfixadmin, setup.php can perform the needed database 
updates automatically .

If you update from 2.1 or older, also create a superadmin account using setup.php.

Note that admin/ has been merged into the main directory. Login with the
superadmin account to setup domains and domain admins.

6. Upgrade your postfix config
------------------------------

Since version 2.3, PostfixAdmin supports alias domains ($CONF['alias_domain']).
If you want to use them, you have to add some queries to your postfix config -
see POSTFIX_CONF for details.


7. Done
-------
This is all that is needed. Fire up your browser and go to the site that you
specified to host Postfix Admin.
