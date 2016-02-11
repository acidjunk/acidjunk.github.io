---
id: 1079
title: Send mail via Gmail from a local postfix server on Ubuntu
date: 2014-12-16T23:22:52+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=1079
permalink: /2014/12/send-mail-via-gmail-from-a-local-postfix-server-on-ubuntu/
categories:
  - Computerz
---
If you want to use Gmail for sending mails from postfix follow this guide.

First, install all necessary packages:

<pre>sudo apt-get install postfix mailutils libsasl2-2 ca-certificates libsasl2-modules
</pre>

If you do not have postfix installed before, postfix configuration wizard will ask you some questions. Just select your server as _Internet Site_ and for FQDN use something you like or if you have a FQDN; use that.

Add the following lines to /etc/postfix/main.cf

<pre>relayhost = [smtp.gmail.com]:587
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_tls_CAfile = /etc/postfix/cacert.pem
smtp_use_tls = yes
</pre>

Create a new file /etc/postfix/sasl_passwd to store the Gmail credentials:

<pre>[smtp.gmail.com]:587    YOURGMAILUSER@gmail.com:YOURGMAILPASSWORD
</pre>

Note: If you want to use your Google App’s domain, just replace @gmail.com with your @yourgoogleappsdomain.com

Fix permission and update postfix config to use sasl_passwd file:

<pre>sudo chmod 400 /etc/postfix/sasl_passwd
sudo postmap /etc/postfix/sasl_passwd
</pre>

Next, validate certificates to avoid running into error. Just run following command:

<pre>cat /etc/ssl/certs/Thawte_Premium_Server_CA.pem | sudo tee -a /etc/postfix/cacert.pem
</pre>

Restart your postfix server:

<pre>sudo /etc/init.d/postfix restart
</pre>

Note: you can ignore errors like: _warning: /etc/postfix/main.cf, line 43: overriding earlier entry: relayhost=_

Test your setup with:

<pre>echo "Hello there, this is a test mail from postfix via Gmail." | mail -s "Test" you@example.com
</pre>

### Troubleshooting

If you run into troubles you probably are sending mail from a new IP of from a Gmail address that wasn&#8217;t used before.

In maillog you will find something like:
  
Error: &#8220;SASL authentication failed; server smtp.gmail.com&#8221;

You need to unlock the captcha by visiting this page https://www.google.com/accounts/DisplayUnlockCaptcha

You can run test again after unlocking captcha.