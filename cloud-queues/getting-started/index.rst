.. _quickstart:
===========================
Quickstart for Cloud Queues
===========================

Queues is an open source, scalable, and highly available message and notifications service, based on the OpenStack Marconi project. Users of this service can create and manage a producer-consumer or a publisher-subscriber model. Unlimited queues and messages give users the flexibility they need to create powerful web applications in the cloud.

It consists of a few basic components: queues, messages, claims, and statistics. In the producer-consumer model, users create queues in which producers, or servers, can post messages. Workers, or consumers, can then claim those messages and delete them after they complete the actions associated with the messages. A single claim can contain multiple messages, and administrators can query claims for status.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

claim
    The process of a worker checking out a message to perform a task. Claiming a message prevents other workers from attempting to process the same message.

message
    A task, a notification, or any meaningful data that a producer or publisher sends to the queue.

queue
    The entity that holds messages. Ideally, a queue is created per work type. 
    For example, if you want to compress files, you would create a queue dedicated to files awaiting compression.

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

Create Queue
--------------

First order of business is creating a queue. In its most basic usage, you can do so as follows:

.. include:: samples/create_queue.rst


List Queues
------------

To see a list of all the queues in a given region, see code below

.. include:: samples/list_queues.rst

Delete Queue
--------------

You may delete a queue, you may do so as follows:

.. include:: samples/delete_queue.rst

Warning: deleting a queue will also delete all messages within it.

Post Message
--------------

Having an empty queue is not that interesting or useful. To remedy that, you should post messages to it. To do so, follow examples below:

.. include:: samples/post_message.rst


Claiming Messages
-------------------

On the other side of that model, the consumer of those messages can claim messages as follows:

.. include:: samples/claim_message.rst


Releasing Claimed Messages
---------------------------

If for whatever reason the consumer cannot complete the task specified in a message or simply refuses to do so, it can release the claim so that a different consumer could attempt to process the message, as shown below:

.. include:: samples/release_message.rst

Deleting Messages
-------------------

After a message has been used or completed and is no longer needed, a consumer should delete the message to avoid duplicate work by other consumers of the queue. Deleting a message can be done as follows:

.. include:: samples/delete_message.rst

More information
================
This Quickstart is intentionally very brief, demonstrating only a few basic operations. 
If you want to know more, these are some good places to continue exploring:

* http://developer.rackspace.com/ links to all our Software Development Kits. It also offers developer-focused support resources such as our IRC channel.

* http://docs.rackspace.com/ links to all our API reference documentation, where you can find additional examples and extended explanations of key concepts. It also links to our documentation for control panel users.

* https://community.rackspace.com/developers/default is a forum where you can discuss your questions and concerns with a community of Rackers, Rackspace customers, and others interested in developing software in the cloud.
