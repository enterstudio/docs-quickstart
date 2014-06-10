.. _quickstart:
==================================
Quickstart for Cloud Block Storage
==================================
Cloud Block Storage provides dependable performance for your I/O-intensive applications by providing a block level storage solution that allows you to mount drives or volumes to your Next Generation Cloud Serversª. 
The two primary use cases are (1) to allow you to scale your storage independently from your compute resources 
and (2) to allow you to utilize high performance storage to serve database or I/O-intensive applications.

You have your choice of SSD or standard volumes. 

* *Standard* volumes work well for your everyday file system needs.

* *SSD* volumes deliver even higher performance for databases and other I/O-intensive applications. 

Plus, you don't have to scale up your servers; both standard and SSD volumes work with all sizes of next-generation Cloud Servers.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

snapshot
    A point-in-time copy of the data that a volume contains. 
    Snapshots are incremental, so each time that you create a snapshot, 
    the incremental changes for the new snapshot are appended to the previous snapshot, which is still available.

volume
    A detachable block storage device. 
    You can think of it as a USB hard drive. 
    You can attach a volume to one instance at a time.

Authenticate to gain access to the service
==========================================
To use this service, you must authenticate yourself as a subscriber to the service.
Authenticate by presenting valid Rackspace customer credentials in a ``POST`` to a Rackspace authentication endpoint.

You can use either of two sets of credentials:

* your username and password
* your username and API key

Your username and password are the ones you use to login to the `Cloud Control Panel <https://mycloud.rackspace.com>`_.
You can obtain or create your API key if you are logged in to the Cloud Control Panel: click on your username, then Account Settings; then under Login Details, you can show or reset your API key. 

After you authenticate, you'll have two things:

* a token, proving that your identity has been authenticated
* a service catalog, listing the API endpoints available to you

To begin interacting with a service, send your token to that service's API endpoint.

.. include:: samples/authentication.rst

Use the API
===========
Some of the basic operations you can perform with this API are described below.

Volume operations
-----------------
You can perform create, read, update, and delete operations on volumes.

Create volume
~~~~~~~~~~~~~
To create a block storage volume in its basic form:

.. include:: samples/create_volume.rst

List volumes
~~~~~~~~~~~~
To see a list of all the block storage volumes you have created in a single region:

.. include:: samples/list_volumes.rst

Show volume
~~~~~~~~~~~
To inspect a specific volume's state:

.. include:: samples/show_volume.rst

Update volume
~~~~~~~~~~~~~
To modify a volume's display name and/or description:

.. include:: samples/update_volume.rst

Delete volume
~~~~~~~~~~~~~
To delete a volume when it is no longer in use (attached) and the data it contains is not needed:

.. include:: samples/delete_volume.rst

Note: please be advised that deleting a volume deletes all the data within it and cannot be recovered unless such data was previously backed up.

Snapshot operations
-------------------
You can perform create, read, update, and delete operations on snapshots.

Create snapshot
~~~~~~~~~~~~~~~
To create a snapshot of a block storage volume:

.. include:: samples/create_snapshot.rst

List snapshots
~~~~~~~~~~~~~~
To see all the snapshots you have created in a given region:

.. include:: samples/list_snapshots.rst

Show snapshot details
~~~~~~~~~~~~~~~~~~~~~
To inspect detailed metadata of a specific snapshot:

.. include:: samples/show_snapshot.rst

Update snapshot
~~~~~~~~~~~~~~~
To modify a snapshot's display name and/or description:

.. include:: samples/update_snapshot.rst

Delete snapshot
~~~~~~~~~~~~~~~
To permanently delete a snapshot:

.. include:: samples/delete_snapshot.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for Cloud Control Panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
