---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}

What is it ?
------------------
Postfix Admin is a:
- A web based interface used to manage mailboxes, virtual domains and aliases for a mailserver
- Also support for vacation/out-of-the-office messages

Requirements
-------------------------------
- Postfix (success has been reported with Exim!)
- MySQL or PostgreSQL
- PHP v4 or v5 should both work
- And presumably a compatible IMAP/POP3 server (dovecot and courier seem to be the most popular circa 2015)

License
-------------------
Postfixadmin is free open source software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

If you make changes to it, or fix bugs, please consider donating your changes back to the community.

Community
----------------------------
Postfixadmin Discussion Forum
IRC - #postfixadmin on irc.freenode.net irc://irc.freenode.net #postfixadmin



Plans...

Release 3.0 - Smarty refactoring, big code cleanup, use PHP classes, easy customization, better vacation functionality, user controllable fetchmail, commandline client
Download - version 2.3

Download the latest release

Version 2.3 was released October 26th 2009, followed by several 2.3.x releases.

New features/changes/things of significance in 2.3.x:

Improved Aliased domains support (no longer relying on catch-all domains) - Note this requires Postfix configuration changes; old configuration(s) will continue to work.
Security fix for setup.php (password required to access; setup.php can generate this and help you)
Superadmin can now setup fetchmail for all users
Enhanced fetchmail.pl script (file locking, syslog logging, configuration file etc)
Added dovecot quota support (documentation + viewing in Postfixadmin) for dovecot 1.0/1.1 and >= 1.2
Vacation re-notification after defineable timeout (default remains to notify only once)
Refactoring of /users (see /model) and XmlRpc interface for remote mail clients (E.g. squirrelmail-postfixadmin)
Add dovecot password support (see here)
Added support for courier authlib authentication flavours ($CONF['authlib_default_flavor'])
update.php should handle all database updates for you
Lots of small updates and random new minor features
bug fixes, better Debian installer.
Many thanks to all those who submitted patches and feedback during this release cycle. There are too many to easily name - we'd like to thank you all for taking the time to help make Postfixadmin better

Download - Development/Subversion release

'trunk' currently contains a working preview of what will be the 3.0 release (see "Plans" above for details of new features). The web interface should work without problems (even if WIP), the commandline client is not fully functional yet.

svn co http://svn.code.sf.net/p/postfixadmin/code/trunk postfixadmin-code
Upgrading Postfixadmin

The database schema between version 2.1.0 and anything later has changed in a number of ways, you should therefore run the 'upgrade.php' script which should take care of all database changes between revisions. This should run automatically when you hit the application, unless you've deleted 'setup.php'.

Other Relevant links and related projects

Postfixadmin/Squirrelmail plugin - Integrate together Squirrelmail with Postfixadmin
Postfixadmin/Roundcube plugin - Integrate together RoundCube with Postfixadmin
Guide to installation on Debian with PostgreSQL and Courier
(If you would like to add links to any other relevant projects or documentation, please poke GingerDog on irc)