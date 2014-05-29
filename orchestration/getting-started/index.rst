.. _quickstart:
==================================
Quickstart for Cloud Orchestration
==================================

Rackspace Cloud Orchestration is the name of the Rackspace orchestration, and application architecture management service.  Cloud Orchestration provides a software API to create and manipulate stacks of resources (for example load balancers, web servers, databases, and so forth) and software that operates as part of those stacks (for example Apache, PHP, MySQL, Wordpress, and so forth). Cloud Orchestration is an engine that understands Cloud topologies, unlike Chef or Puppet, which are concerned with software on servers. Where applicable, Cloud Orchestration leverages software configuration management tools such as Chef. Using simple template syntax, you can define a cloud stack, deploy the stack, scale the stack (for example add/remove resources), delete the stack, clone the stack, and more.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

resource
    A template artifact that represents some component of your desired architecture 

stack
    A running instance of a template. The result of creating a stack is a deployment of the application framework or component.

template
    A file that describes how a set of resources should be assembled and what software should be installed to produce a working deployment.

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

Use the API
===========

Create Stack
-------------

After you have created your stack template, you can then create the stack in the Rackspace cloud in the following manner: 

.. include:: samples/create_stack.rst

List Stacks
------------

If you want to see the stacks you have already deployed in a given region, you may do so as follows:

.. include:: samples/list_stacks.rst


Get Stack Data
---------------

If you want to inspect a single stack's detail data, you can do so as shown below:

.. include:: samples/get_stack_data.rst

Update Stack
-------------

In the event that you wish to update or modify an existing stack, the code sample below demonstrate how it can be done:

.. include:: samples/update_stack.rst

Delete Stack
-------------

Once you no longer wish to track a stack and destroy all resources the stack has provisioned, you can delete said stack as follows:

.. include:: samples/delete_stack.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for control panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
