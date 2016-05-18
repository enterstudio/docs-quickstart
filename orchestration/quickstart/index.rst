



==================================
Quickstart for Cloud Orchestration
==================================

Rackspace Cloud Orchestration is the name of the Rackspace orchestration and application architecture management service.
Cloud Orchestration provides a software API to create and manipulate stacks of resources (for example load balancers, web servers, and databases) and software that operates as part of those stacks (for example Apache, PHP, MySQL, and Wordpress).
Cloud Orchestration is an engine that understands cloud topologies; in this way, it is unlike Chef or Puppet, which are concerned with software on servers.
Where applicable, Cloud Orchestration leverages software configuration management tools such as Chef.
Using simple template syntax, you can define a cloud stack, deploy the stack, scale the stack (for example, add or remove resources), delete the stack, clone the stack, and more.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

resource
    A template artifact that represents some component of your desired architecture.

stack
    A running instance of a template. The result of creating a stack is a deployment of the application framework or component.

template
    A file that describes how a set of resources should be assembled and what software should be installed to produce a working deployment.

.. include:: ../../_common/authenticate.rst

.. include::  samples/authentication.rst

Use the API
===========
Some of the basic operations you can perform with this API are described below.

Create stack
------------
After you have created your stack template, you can create the stack in the Rackspace cloud:

.. include:: samples/create_stack.rst

List stacks
-----------
To see the stacks you have already deployed in a given region:

.. include:: samples/list_stacks.rst

Get stack data
--------------
To inspect a single stack's detail data:

.. include:: samples/get_stack_data.rst

Update stack
------------
To update or modify an existing stack:

.. include:: samples/update_stack.rst

Delete stack
------------
To delete a stack and destroy all resources the stack has provisioned:

.. include:: samples/delete_stack.rst

.. include:: ../../_common/moreinfo.rst
