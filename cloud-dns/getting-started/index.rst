.. _quickstart:

Quickstart Guide
=================

Cloud DNS
---------------

Rackspace offers a flexible and scalable solution to DNS management through its CloudDNS service.

Authentication and client creation
----------------------------------
To use the API, you must authenticate and create an instance of the appropriate API client.

.. include:: samples/authentication.rst

Create Zone
-----------------

The first step in managing your domains and subdomains is to create a DNS zone, which you can think of as being the "root" level. So, for example, you have a domain called `domain.com`, create a zone called `domain.com` via the DNS service as follows:

.. include:: samples/create_zone.rst

Get Zone
------------------

After you create a zone, you can retrieve it and inspect its details as follows:

.. include:: samples/get_zone.rst

Modify Zone
-------------------

You can modify your DNS zone if any of the details change, so long as the  new values are valid (i.e. correct email address format, TTL > 300s, etc.); however, the zone name is cannot be changed. Thus, if you need to modify the zone name, delete the zone (explained below) and create another one with the new domain.

.. include:: samples/modify_zone.rst

Delete Zone
---------------

To delete a DNS zone:

.. include:: samples/delete_zone.rst

**WARNING: deleting a zone will also delete all the records within it. Please use with care.**

Create Record
--------------

After you create a zone, you will normally add at least one record to it so that it will be useful. For example, an `A` record gives the IP address of the domain or a subdomain, while a `CNAME` creates an alias (a *canonical* name) to another record.

To create a DNS zone record:

.. include:: samples/create_record.rst

Get Record
-------------

If the zone has one or more records, you can retrieve them for inspection or manipulation as follows:

.. include:: samples/get_record.rst

Update Record
---------------

To modify a DNS record:

.. include:: samples/modify_record.rst

Delete Record
----------------

To delete a DNS record:

.. include:: samples/delete_record.rst
