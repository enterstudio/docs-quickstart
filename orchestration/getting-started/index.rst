.. _quickstart:
==================================
Quickstart for Cloud Orchestration
==================================

Rackspace Cloud Orchestration is the name of the Rackspace orchestration, and application architecture management service.  Cloud Orchestration provides a software API to create and manipulate stacks of resources (for example load balancers, web servers, databases, and so forth) and software that operates as part of those stacks (for example Apache, PHP, MySQL, Wordpress, and so forth). Cloud Orchestration is an engine that understands Cloud topologies, unlike Chef or Puppet, which are concerned with software on servers. Where applicable, Cloud Orchestration leverages software configuration management tools such as Chef. Using simple template syntax, you can define a cloud stack, deploy the stack, scale the stack (for example add/remove resources), delete the stack, clone the stack, and more.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

term(resource)
    A template artifact that represents some component of your desired architecture 

term(stack)
-----
    A running instance of a template. The result of creating a stack is a deployment of the application framework or component.

term(template)
    A file that describes how a set of resources should be assembled and what software should be installed to produce a working deployment.

Authentication
--------------

To use the API, authenticate and create an instance of the appropriate API client.

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

