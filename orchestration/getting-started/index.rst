.. _quickstart:

Quickstart Guide
=================

Cloud Orchestration
--------------------

Rackspace Cloud Orchestration is the name of the Rackspace orchestration, and application architecture management service.  Cloud Orchestration provides a software API to create and manipulate stacks of resources (for example load balancers, web servers, databases, and so forth) and software that operates as part of those stacks (for example Apache, PHP, MySQL, Wordpress, and so forth). Cloud Orchestration is an engine that understands Cloud topologies, unlike Chef or Puppet, which are concerned with software on servers. Where applicable, Cloud Orchestration leverages software configuration management tools such as Chef. Using simple template syntax, you can define a cloud stack, deploy the stack, scale the stack (for example add/remove resources), delete the stack, clone the stack, and more.

Authorization
--------------

Before we can use the API, we need to authenticate and create an instance of the appropriate API client.

.. include:: samples/authentication.rst

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

