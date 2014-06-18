.. _quickstart:
===========================
Quickstart for Cloud Images
===========================

Rackspace Cloud Images enables you to create and manipulate filesystem snapshots of your Cloud Servers. Images that you capture are stored in Cloud Files.

Images that you create can also be shared with other Rackspace accounts.

Concepts
========

To use this service effectively, you should understand these key ideas:

Image
    A bundle of operating system (OS) files that you use to create or rebuild a server. There are pre-defined images, but you can also create your own custom images from servers that you've launched. Custom images can be used as data backups or as *gold* images used to launch additional servers.

    * A **standard image** is one that Rackspace supplies for your service level, or that is provided specifically for RackConnect customers, and that hasn't yet reached its end-of-life.

    * A **nonstandard image** is one that is imported or exported, end-of-life, shared, not standard for your account service level, or not included in the subset of images provided for RackConnect customers.

Image Member
    A user who has been granted access to an image, identified by Rackspace account number.

Authenticate to gain access to the service
==========================================

To use this service, you must authenticate yourself as a subscriber to the service.
Authenticate by presenting valid Rackspace customer credentials in a ``POST`` to a Rackspace authentication endpoint.

You can use either of two sets of credentials:

* your username and password
* your username and API key

Your username and password are the ones you use to login to the Cloud Control Panel at http://mycloud.rackspace.com/.
You can obtain or create your API key if you are logged in to the Cloud Control Panel: click on your username, then Account Settings; then under Login Details, you can show or reset your API key.

Your username and password are the ones you use to login to the Cloud Control Panel at http://mycloud.rackspace.com/.

To find your API key, first navigate to the Cloud Control Panel, then click on your username at the top right corner, and then finally click on Account Settings. You will be taken to a page that shows your settings. Under Login Details, you can show or reset your API key.

Once you have these pieces of information, you can pass them into the SDK:

.. include:: samples/authentication.rst

Image operations
================

List available images
---------------------

To see the images that are currently available to your account:

.. include:: samples/list_images.rst

Get image details
-----------------

Once you know the ID of an image that you care about, you can access additional information and metadata:

.. include:: samples/get_image.rst

Update image
------------

Each image can have arbitrary metadata associated with it. You can update the metadata for a specific image:

.. include:: samples/update_image.rst

Import or export image
----------------------
An image task is a request to perform an asynchronous image-related operation, such as importing or exporting an image.
The request results in the creation of a disposable task resource that can be polled for information about the status of the operation.

After you initiate an image import or export, poll the status of the created task.
When the task resource reaches a final status of success or failure, the poll response includes an expiration date and time stamp. After that expiration date and time, the disposable task resource itself expires and is subject to deletion.
However, the result of the task, such as an imported or exported image, does not expire.

.. include:: samples/import_image.rst

.. include:: samples/export_image.rst

Share image
-----------
You can perform create, read, update, and delete operations on image members.
The Cloud Images API enables you and others to share your custom images.

Note:
The operations you can execute depend on your role.
If you are an image producer, you cannot use the update_image_member operation for an image you are sharing with someone else.
Likewise, if you are an image consumer you cannot use create_image_member for someone else's image.

Add image member
~~~~~~~~~~~~~~~~
.. include:: samples/create_image_member.rst

List image members
~~~~~~~~~~~~~~~~~~
.. include:: samples/list_image_members.rst

Get image member details
~~~~~~~~~~~~~~~~~~~~~~~~
.. include:: samples/get_image_member.rst

Update image member
~~~~~~~~~~~~~~~~~~~
.. include:: samples/update_image_member.rst

Delete image member
~~~~~~~~~~~~~~~~~~~
.. include:: samples/delete_image_member.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations.
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for Cloud Control Panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
