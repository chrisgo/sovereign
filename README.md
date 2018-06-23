# Introduction

* This was a fork of http://github.com/sovereign/sovereign (follow most of the steps here first)
* Found this article: https://thomas-leister.de/en/mailserver-debian-stretch/ so will start incorporating some of the items here into this project.  Specifically, this article tells you exactly what you will get at the end of doing all this work (like IMAP/POP3/SMTP settings, etc.) - will update this more as things progress
* Also some concepts taken from http://mailinabox.email

# Goals

* Have a server at DigitalOcean running Debian 64-bit 9.x "stretch" that runs all mail related services for one (primary) or more domains
* Admin UI: https://mail.domain.com (primary domain)
* Provide you with DNS entries
  *
* Provide you with settings that will work for your mail client
  * POP3 Server:
  * IMAP Server:
  * SMTP Server:
  * Also provide a webmail interface
* Create 2nd playbook to enable you to add 2nd, 3rd, 4th domains to provide mail services for after the initial setup

# Fork Notes

* Targets Debian 9.x "stretch" (DO Debian 64-bit 9.4)
* Focuses on running a mail server (closer to only what is in https://mailinabox.email/)
  - IMAP over SSL via Dovecot, complete with full text search provided by Solr.
  - POP3 over SSL, also via Dovecot
  - SMTP over SSL via Postfix, including a nice set of DNSBLs to discard spam before it ever hits your filters.
  - Virtual domains for your email, backed by PostgreSQL.
  - Spam fighting via Rspamd.
  - Mail server verification using DKIM and DMARC so the Internet knows your mailserver is legit.
  - Secure on-disk storage for email and more via EncFS (not 100% sure what this doing yet).
  - Webmail via Roundcube.
  - <del>Mobile push notifications via Z-Push</del>.
  - <del>Email client automatic configuration</del>.
  - <del>Jabber/XMPP instant messaging via Prosody</del>.
  - <del>An RSS Reader via Selfoss</del>.
  - <del>CalDAV and CardDAV to keep your calendars and contacts in sync, via ownCloud</del>.
  - <del>Your own private storage cloud via [ownCloud</del>.
  - <del>Your own VPN server via OpenVPN</del>.
  - <del>An IRC bouncer via ZNC</del>.
  - <del>Monit</del>.
  - <del>collectd</del>.
  - <del>Web hosting (ex: for your blog) via Apache</del>.
  - TODO: Firewall management via [Uncomplicated Firewall (ufw).
  - TODO: Intrusion prevention via fail2ban and rootkit detection via rkhunter.
  - TODO: SSH configuration preventing root login and insecure password authentication
  - <delRFC6238 two-factor authentication compatible with Google Authenticator and various hardware tokens</del>
  - <del>Nightly backups to Tarsnap</del>.
  - <del>Git hosting via cgit and gitolite</del>.
  - <del>Read-it-later via Wallabag</del>
  - TODO: A bunch of nice-to-have tools like mosh and htop that make life with a server a little easier.
* TODO: Use Nginx as web server (instead of Apache)
* TODO: Use Mariadb (MySQL) as database server (instead of Postgres)
* Use Tomcat8 for Solr (instead of Tomcat7) - default tomcat in Debian 9
* Fix deprecation warning: `state=installed` to `state=present`
* TODO: Fix deprecation warning: The sudo command line option has been deprecated in favor of the "become" command line arguments
