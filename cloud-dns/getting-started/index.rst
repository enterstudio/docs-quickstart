.. _quickstart:
========================
Quickstart for Cloud DNS
========================
Rackspace offers a flexible and scalable solution to DNS management through its CloudDNS service.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

domain
    An entity containing all DNS-related information.

zone
    A single manager's scope of control within the domain name space.

Authenticate to gain access to the service
==========================================
To use this service, you must authenticate yourself as a subscriber to the service.
Authenticate by presenting valid Rackspace customer credentials in a ``POST`` to a Rackspace authentication endpoint.

You can use either of two sets of credentials:

* your username and password
* your username and API key

Your username and password are the ones you use to login to the Cloud Control Panel at http://mycloud.rackspace.com/. 
You can obtain or create your API key if you are logged in to the Cloud Control Panel: click on your username, then Account Settings; then under Login Details, you can show or reset your API key. 

After you authenticate, you'll have two things:

* a token, proving that your identity has been authenticated
* a service catalog, listing the API endpoints available to you

To begin interacting with a service, send your token to that service's API endpoint.

.. include:: samples/authentication.rst

Use the API
===========
Some of the basic operations you can perform with this API are described below.

Zones
-----
You can perform create, read, update, and delete operations on zones.

Create zone
~~~~~~~~~~~
The first step in managing your domains and subdomains is to create a DNS zone, which you can think of as being the "root" level. So, for example, you have a domain called `domain.com`, create a zone called `domain.com` via the DNS service as follows:

.. include:: samples/create_zone.rst

Get zone
~~~~~~~~
After you create a zone, you can retrieve it and inspect its details as follows:

.. include:: samples/get_zone.rst

Modify zone
~~~~~~~~~~~
You can modify your DNS zone if any of the details change, so long as the  new values are valid (i.e. correct email address format, TTL > 300s, etc.); however, the zone name is cannot be changed. Thus, if you need to modify the zone name, delete the zone (explained below) and create another one with the new domain.

.. include:: samples/modify_zone.rst

Delete zone
~~~~~~~~~~~
To delete a DNS zone:

.. include:: samples/delete_zone.rst

**WARNING: deleting a zone will also delete all the records within it. Please use with care.**

Records
-------
You can perform create, read, update, and delete operations on records.

Create record
~~~~~~~~~~~~~
After you create a zone, you will normally add at least one record to it so that it will be useful. For example, an `A` record gives the IP address of the domain or a subdomain, while a `CNAME` creates an alias (a *canonical* name) to another record.

To create a DNS zone record:

.. include:: samples/create_record.rst

Get record
~~~~~~~~~~
If the zone has one or more records, you can retrieve them for inspection or manipulation as follows:

.. include:: samples/get_record.rst

Update record
~~~~~~~~~~~~~
To modify a DNS record:

.. include:: samples/modify_record.rst

Delete record
~~~~~~~~~~~~~
To delete a DNS record:

.. include:: samples/delete_record.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for Cloud Control Panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
