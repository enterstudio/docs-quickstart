.. _quickstart:
==================================
Quickstart for Cloud Block Storage
==================================

Rackspace Cloud Block Storage is a block level storage solution that allows customers to mount drives or volumes to their Rackspace Next Generation Cloud Servers™. The two primary use cases are (1) to allow customers to scale their storage independently from their compute resources, and (2) to allow customers to utilize high performance storage to serve database or I/O-intensive applications.

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

Authenticating
===============

In order to authenticate, you need a username and API key which you can find in the control panel by visiting the "Account Settings" page.

Once you've retrieved your details, you pass them into the client:

.. include:: samples/authentication.rst

Volume Operations
==================

Create Volume
--------------
To create a block storage volume, in its basic form, you can do as follows:

.. include:: samples/create_volume.rst

List Volumes
-------------

In order to see a list of all the block storage volumes you have created in any one given region, follow the code below:

.. include:: samples/list_volumes.rst

Show Volume
-------------

The code below shows how to inspect a specific volume's state:

.. include:: samples/show_volume.rst

Update Volume
-----------------

To modify a volume's display name and/or description, follow the code shown below:

.. include:: samples/update_volume.rst

Delete Volume
--------------

Once a volume is no longer in use (attached) and the data it contains is not needed, you can delete it as follows:

.. include:: samples/delete_volume.rst

Note: please be advised that deleting a volume deletes all the data within it and cannot be recovered unless such data was previously backed up.

Snapshots Operations
=====================

Create Snapshot
----------------

To create a snapshot of a block storage volume, simply follow the code below:

.. include:: samples/create_snapshot.rst

List Snapshots
---------------

To see all the snapshots you have created in a given region, you can do as follows:

.. include:: samples/list_snapshots.rst

Show Snapshot Details
----------------------

To inspect detailed metadata of a specific snapshot, do so as shown below:

.. include:: samples/show_snapshot.rst

Update Snapshot
-----------------

To modify a snapshot's display name and/or description, follow the code shown below:

.. include:: samples/update_snapshot.rst

Delete Snapshot
-----------------

To permanently delete a snapshot you can do as follows:

.. include:: samples/delete_snapshot.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.
* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. 
It also links to our documentation for control panel users.
* https://community.rackspace.com/developers/ is a forum where you can discuss your questions and concerns with 
a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
