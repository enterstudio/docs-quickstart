.. _quickstart:
===========================
Quickstart for Cloud Images
===========================

This guide helps you get started with the Rackspace Cloud Images service.

This service enables you to create and
manipulate images, image members, and associated metadata through
a simple Representational State Transfer (REST) web service interface.

This service is closely aligned with the Rackspace Cloud Servers
and Cloud Files services. 

Images are captured from, and applied to, cloud servers
and are stored on, and retrieved from, Cloud Files storage.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

server
    A computer that provides explicit services to the client software running on that system. 
    A server is a virtual machine (VM) instance in the Cloud Servers environment. 
    To create a server, you must specify a name, flavor reference, and image reference.

flavor
    A resource configuration for a server. 
    Each flavor is a unique combination of disk, memory, vCPUs, and network bandwidth.
    You can choose from pre-defined flavors.
    
network
    The virtual space where your servers live. Rackspace has two default networks: 
    PublicNet, which is the Internet; ServiceNet, which is our internal network.
    Although you can create as many isolated networks as you want, 
    the default configuration is for servers to be connected to 
    both PublicNet (for public Internet connectivity) and ServiceNet (for internal connectivity with your other servers).

image
    A collection of specific operating system (OS) files that you use to create or rebuild a server. 
    You can choose from pre-defined images or create your own custom images 
    from servers that you have launched. 
      
      You can use custom images for data backups and 
      as *gold* images to launch additional servers. 
      
    * A **standard image** is one that has not reached its end of life 
      and that Rackspace supplies for your service 
      level or that is provided specifically for RackConnect customers. 
      
    * A **nonstandard image** is one that is imported or exported, end-of-life, shared, 
      not standard for your account service level and not included
      in the subset of images provided for RackConnect customers.

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
These are some of the the basic operations you can perform with this API.

Image entity
------------
An image entity is represented by a JSON-encoded data structure and its raw binary data. 
An image entity has an identifier (ID) that is guaranteed to be unique within its endpoint. 
The ID is used as a TOKEN in request URIs to interact with that specific image. 
An image is always guaranteed to have the following attributes: 
``id``,
``status``,
``visibility``,
``protected``,
``tags``,
``created_at``,
``file``, and
``self``.

The other attributes defined in the image schema are guaranteed, but are only returned with an image entity if you set them explicitly.

A client can set arbitrarily-named attributes on their images if the image JSON-schema allows it. 
These user-defined attributes appear like any other image attributes.

Image identifiers
-----------------
Images are uniquely identified by a URI that matches this signature::

  {image server location}/v2/images/{imageId}

where:

* ``{image server location}`` is the resource location of the Cloud Images service that knows about an image.
* ``{imageId}`` is the image identifier, which is a UUID, making it globally unique.

Common image properties
-----------------------
To help end users use your images, you can put additional common properties, or metadata, on your images.

The available properties and their expected values include:

**os_distro**
  The common name of the operating system          
  distribution. 
  
  Must be all lowercase and          
  entered exactly as shown here:                                      

  - arch. Arch Linux                               
  - centos. Community Enterprise Operating System  
  - debian. Debian                                 
  - fedora. Fedora                                 
  - freebsd. FreeBSD                               
  - gentoo. Gentoo Linux                           
  - mandrake. Mandrakelinux (MandrakeSoft)         
  - mandriva. Mandriva Linux                       
  - mes. Mandriva Enterprise Server                
  - msdos. Microsoft Disk Operating System         
  - netbsd. NetBSD                                 
  - netware. Novell NetWare                        
  - openbsd. OpenBSD                               
  - opensolaris. OpenSolaris                       
  - opensuse. openSUSE                             
  - rhel. Red Hat Enterprise Linux                 
  - sled. SUSE Linux Enterprise Desktop            
  - ubuntu. Ubuntu                                 
  - windows. Microsoft Windows                     

**os_version**   
  The distributor-specified OS version.
    

Use images
----------
To see which images are available, you can list all images or get details for a specified image.
Then, you can update an image and use image tasks to import and export images.

List images and get image details
---------------------------------
An image, or operating system, forms the basis of your server. 
Each image has a unique ID, which you can use to get more details about the image.

To list images:

.. include:: samples/list_images.rst

Once you know the image ID, you can get more details about the image:

.. include:: samples/get_image.rst

Once you've found the desired operating system, and its ID, you can move on to picking your hardware.

Update image
------------
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

Share images
------------
You can perform create, read, update, and delete operations on image members.
The Cloud Images API enables you and others to share your custom images.  

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
