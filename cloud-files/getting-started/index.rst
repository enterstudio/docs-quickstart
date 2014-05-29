.. _quickstart:
==========================
Quickstart for Cloud Files
==========================
Rackspace offers a flexible and scalable solution to object storage through its Cloud Files service. The intent of this guide to get you up and running with Cloud Files as quick as possible. If your case is not covered in the samples below, you might want to check out SDK-specific documentation for much deeper treatment of the subjects below as well as use cases purposely left out.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

CDN (Content Delivery Network)
    A network of high-availability servers delivering content to users. Cloud Files uses the Akamai CDN.

container
    A storage compartment that provides a way for you to organize your data.

object
    The basic storage entity in Cloud Files. 
    An object represents a files and its optional metadata that you upload to the system.

Authenticate to gain access to the service
==========================================
To use this service, you must authenticate yourself as a subscriber to the service.
Authenticate by presenting valid Rackspace customer credentials in a ''POST'' to a Rackspace authentication endpoint.

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

Create Container
-----------------

Before we can upload any objects to Cloud Files, we first must create a container. In its simplest form a container can be created as follows:

.. include:: samples/create_container.rst


Set Container as CDN
----------------------

Once we have created a container, we can set it as CDN (Content Delivery Network). That implies that any objects within the container will be publicly readable. To set a container as CDN can be accomplished as follows:

.. include:: samples/set_container_as_cdn.rst


Unset Container as CDN
-----------------------

If you no longer wish to have your container set as CDN, you may do as as described in the code below:

.. include:: samples/unset_container_as_cdn.rst


Delete Container
-----------------

In that event that you need to delete a container, you can do so as shown below (please note that for data safety reasons you may not delete a container until **all** objects within it have been deleted):

.. include:: samples/delete_container.rst


Uploading Objects to Container
-------------------------------

Once we have a container, we can then upload objects to it in the following manner:

.. include:: samples/upload_object.rst


Change Object Metadata
------------------------

Once you have an object uploaded to a container it is possible to change its metadata in-place. For instance, you can change its content-type so that when delivered to requesting clients it can be treated accordingly. The code snippet below shows how:

.. include:: samples/change_object_metadata.rst

Getting Objects
---------------

We (and clients) can retrieve objects from Cloud Files in several ways. Below we explain the most common ways.

Get Object via Temporary URL
-----------------------------

To retrieve an object via temporary URL, see the example below:

.. include:: samples/get_object_temp_url.rst


Get Object Directly (i.e. download via SDK)
---------------------------------------------

You may also download objects directly into your local storage drive via SDK download. To do so, see the following code example:

.. include:: samples/get_object_sdk.rst


Get Object via CDN URL
-------------------------

Another common way of getting objects is through CDN URLs, which, unlike temporary URLs, never expire and may considered publicly-accessible "permalinks"

.. include:: samples/get_object_cdn.rst

Delete Objects
---------------

To delete objects, consider the code below:

.. include:: samples/delete_object.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for control panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
