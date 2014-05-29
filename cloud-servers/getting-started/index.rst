.. _quickstart:
============================
Quickstart for Cloud Servers
============================

This guide will provide an introduction to Rackspace Cloud Servers, describing what it is and what it can do. In a nutshell, it is a service that allows you to allocate and deallocate compute resources. It is based on OpenStack Compute (Nova), a community-led open-source platform.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

server
    A computer that provides explicit services to the client software running on that system. 
    A server is a virtual machine (VM) instance in the Cloud Servers environment. 
    To create a server, you must specify a name, flavor reference, and image reference.

image
    The type of operating system you want to use. 
    You can choose from pre-defined images or create your own custom images.

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

Setting up your first server
============================

Once you've finished your initial setup, you can begin the process of creating your first server.

In order to do this, you need to decide which **Image** and **Flavor** you want to use.

Task 1: Finding an Operating System
-----------------------------------

An Image, or operating system, will form the basis of your server. Each one has a unique ID, which is used to retrieve more details from the API. If you already know the ID, you can retrieve more details about the image like this:

.. include:: samples/get_image.rst

Alternatively, you can traverse through the list:

.. include:: samples/list_images.rst

Once you've found the perfect operating system, and its ID, you can move on to picking your hardware.

Task 2: Finding the right hardware
----------------------------------

Flavors, or hardware configurations, will dictate how powerful your servers are. Like images, each flavor has its own UUID. If you already know which flavor to use, you can retrieve its details like this:

.. include:: samples/get_flavor.rst

Alternatively, you can traverse through the standard list Rackspace provides:

.. include:: samples/list_flavors.rst

Task 3: Putting the pieces together
-----------------------------------

Now that we have our image ID and flavor ID, you can create your server:

.. include:: samples/create_server.rst

This is an asyncronous operation, meaning that it will _not_ block your request until the process is complete. It will provision your VM behind the scenes, allowing you to optionally query its status. Once the build reaches a ``COMPLETE`` state, it will be available for you to use.

Some SDKs allow you to check on the status of the build:

.. include:: samples/query_server_build.rst

Deleting your server
--------------------

If you've finished working with your server, you can permanently delete it like so:

.. include:: samples/delete_server.rst

Managing key pairs
==================

By default, servers will use password-based authentication. When a server is created, the HTTP response will contain a root password that is required for all subsequent SSH connections. You do have the option, however, of using keypairs instead.

Registering your keypair
------------------------

In order to use keypair-based authentication, the API needs to know about it. You have two options: upload your existing key, or have the API create a new one for you. We'll cover both.

Upload an existing keypair:

.. include:: samples/upload_existing_keypair.rst

Or have the API create one for you:

.. include:: samples/create_new_keypair.rst

Using keypairs
--------------

If you want an existing server to use keypair-based auth, you will need to configure this yourself.

However, getting new servers to acknowledge keypairs is easy. You just need to supply the name of the pre-existing keypair when you do the create server operation, like this:

.. include:: samples/create_server_with_keypair.rst

This server, after being spun up, will respond to that keypair.

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for control panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
