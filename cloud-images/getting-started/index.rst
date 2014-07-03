.. _quickstart:
===========================
Quickstart for Cloud Images
===========================

Cloud Images are filesystem snapshots of your Cloud Servers. You can use them to duplicate Cloud Servers, and even share images across multiple Rackspace accounts.

Concepts
========

Image
    A bundle of files that you use to create or rebuild a server. There are pre-defined images, but you can also create your own custom images from servers that you've launched.

    * A **standard image** is a Rackspace provided image, like *Fedora 20 (Heisenbug) (PVHVM)*

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

.. include:: samples/list_images.rst

Get image details
-----------------

Each image can have arbitrary metadata associated with it, which you can use to share information about the image or to aid filtering and sorting.

Once you know the ID of an image that you care about, you can see its additional information and metadata:

.. include:: samples/get_image.rst

Update an image
---------------

You can also update the metadata for a specific image:

.. include:: samples/update_image.rst

Import or export an image
-------------------------

Images can be *imported* and *exported* to and from Cloud Files. This can be useful for moving images between regions.

To export an image to Cloud Files:

.. include:: samples/export_image.rst

To import an image from Cloud Files:

.. include:: samples/import_image.rst

Share an image
--------------

Rackspace Cloud Images enables you and others to share custom images. You accomplish this by manipulating *image members*.

The operations that you can execute on a specific image depend on your role. If you are an image producer, you can't update an image member for an image you're sharing with someone else. Similarly, if you're an image consumer, you can't create additional image members for someone else's image.

First, the image **producer** initiates the sharing process by adding a *member* to the image.

.. include:: samples/create_image_member.rst

The image does **not** automatically appear in the images list for the consuming user. Instead, the **consumer** must explicitly *accept* or *reject* the image member.

.. include:: samples/update_image_member.rst

To check on the status of these transactions, either party can view the image member's details:

.. include:: samples/get_image_member.rst

Both users can also list all of the members for a given image:

.. include:: samples/list_image_members.rst

If you're an image **producer** and you want to unshare an image from another user, you can delete the image member:

.. include:: samples/delete_image_member.rst
