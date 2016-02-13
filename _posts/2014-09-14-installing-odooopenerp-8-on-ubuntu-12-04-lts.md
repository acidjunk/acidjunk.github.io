---
id: 1054
title: Installing Odoo/OpenERP 8 on Ubuntu 12.04 LTS
date: 2014-09-14T00:46:21+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1054
permalink: /2014/09/installing-odooopenerp-8-on-ubuntu-12-04-lts/
categories:
  - Computerz
header-img: "img/post-bg-02.jpg"
---
# What is Odoo?

Recently OpenERP is re-branded to Odoo. OpenERP was primarily an Open Source Enterprise Resource (ERP) software suite of business applications that includes Sales Management, Manufacturing, Purchase Management, E-commerce, POS, Accounting & Finance, CRM, and Project Management, to name just a few. However, having recently released a range of new and diverse applications, and with the promise that by using its system, ‘a business can go from zero to trading online quicker than ever’. 

In new release they have included Website Builder, POS applications and the eCommerce storefront, Timetracker, Employee evaluations, Assets management, An flexible XMLRCP API, Payrolling, Invoice and Quote generator, Blog, the community has moved into a new territory – a territory in which no ERP has gone before.

### Install Odoo (Open ERP v8) on Ubuntu 12.04 from launchpad

So let&#8217;s install it.

<pre>sudo apt-get update
sudo apt-get upgrade
</pre>

Install required packages:

<pre>sudo apt-get install graphviz ghostscript postgresql-client python-dateutil python-feedparser python-matplotlib python-ldap python-libxslt1 python-lxml python-mako python-openid python-psycopg2 python-pybabel python-pychart python-pydot python-pyparsing python-reportlab python-simplejson python-tz python-vatnumber python-vobject python-webdav python-werkzeug python-xlwt python-yaml python-imaging python-gdata python-requests
</pre>

Install supporting packages:

<pre>sudo apt-get install apt-get install gcc python-dev mc bzr python-setuptools python-babel python-feedparser python-reportlab-accel python-zsi python-openssl python-egenix-mxdatetime python-jinja2 python-unittest2 python-mock python-docutils lptools make python-psutil python-paramiko poppler-utils python-pdftools antiword postgres wkhtmltopdf 
</pre>

Create a new system user and database user:

<pre>sudo adduser odoo --home /opt/odoo
sudo -u postgres createuser -s odoo
</pre>

Install Odoo itself:

<pre>sudo su odoo
mkdir /opt/odoo/v8
cd /opt/odoo/v8
bzr branch lp:~openerp/openerp-web/saas-4 web
bzr branch lp:~openerp/openobject-server/saas-4 server
bzr branch lp:~openerp/openobject-addons/saas-4 addons
exit
sudo cp /opt/odoo/v8/server/install/openerp-server.conf /etc/openerp-server.conf
</pre>

Edit configuration (e.g. sudo vim /etc/openerp-server.conf):

<pre>[options]
; This is the password that allows database operations:
admin_passwd = CHOOSE_A_PASS_TO_ADMIN_DBS
db_host = False
db_port = False
db_user = odoo
db_password = False
addons_path = /opt/odoo/v8/addons,/opt/odoo/v8/web/addons
;Log settings
logfile = /var/log/openerp/openerp-server.log
log_level = error
</pre>

Set permissions, setup logging and logrotate:

<pre>sudo chown odoo: /etc/openerp-server.conf
sudo chmod 640 /etc/openerp-server.conf
sudo mkdir /var/log/openerp
sudo chown odoo:root /var/log/openerp
sudo cp /opt/odoo/v8/server/install/openerp-server.logrotate /etc/logrotate.d/openerp-server
sudo chmod 755 /etc/logrotate.d/openerp-server
</pre>

Start the server:

<pre>sudo su odoo
cd /opt/odoo/v8/server/
./openerp-server -c /etc/openerp-server.conf &
</pre>

At the moment Odoo8 is not suitable for production environments; wait for an stable release&#8230;
  
But if you just want to play and fiddle around with the next generation of open source ERP systems; it has a lot of cool new options.