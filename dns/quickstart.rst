.. _quickstart:

Quickstart Guide
=================

Cloud DNS
---------------

Rackspace offers a flexible and scalable solution to DNS management through its CloudDNS service.

Authentication and client creation
----------------------------------
Before we can use the API, we need to authenticate and create an instance of the appropriate API client.

.. include:: samples/authentication.rst

Create Zone
-----------------

The first step to manage your domains and subdomains is to create a DNS zone, which you can think of as being the "root" level. So, say, you have a domain called domain.com, you want to create a zone called domain.com as follows:

.. include:: samples/create_zone.rst

Get Zone
------------------

Once we have created a zone, we can retrieve it and inspect its details as follows:

.. include:: samples/get_zone.rst

Modify Zone
-------------------

We can also modify our DNS zone if any of the details change, with the provision that values passed are valid (i.e. correct email address format, TTL > 300s, etc.); however, the zone name is immutable. Thus if you need to modify zone name, you'll need to delete the zone (explained below) and start anew.

.. include:: samples/modify_zone.rst

Delete Zone
---------------

If you wish or need to delete a DNS zone it can be accomplished as follows:

.. include:: samples/delete_zone.rst

**WARNING: deleting a zone will also delete all the records within in. Please use with care.**

Create Record
--------------

Once we have a zone, we to add at least one record to it in order to make it do something useful. You can create a DNS zone record as follows:

.. include:: samples/create_record.rst

Get Record
-------------

Once we have have created a record, we can retrieve it for inspection or manipulation as follows:

.. include:: samples/get_record.rst

Update Record
---------------

If you wish to modify a DNS record, you can do so as follows:

.. include:: samples/modify_record.rst

Delete Record
----------------

In that event that you need to delete a DNS record, you can do so as shown below:

.. include:: samples/delete_record.rst
