.. _quickstart:
===============================
Quickstart for Cloud Monitoring
===============================

Cloud Monitoring helps you keep a keen eye on all of your resources; from web sites to web servers, routers, load balancers, and more.

Concepts
========
To use this service effectively, you should understand how these key ideas are used in this context:

agent
-----
A monitoring daemon that resides on the server being monitored. 
The agent gathers metrics based on agent checks and pushes them to Cloud Monitoring.

alarm
-----
Contains a set of rules that determine when the monitoring system sends a notification. 
You can create multiple alarms for the different check types associated with an entity

check
-----
Contains the specific details of how you are monitoring the entity, such as
which components of the entity to monitor, the monitoring frequency, and how many monitoring zones are launching the check. 

entity
------
The object or resource that you want to monitor. 
An entity is commonly a web server, but it might also be a website, a web page, or a web service.

notification
------------
An informational message sent to one or more addresses by the monitoring system when an alarm is triggered.

Workflow
===========
* Create an entity to represent the item you want to monitor. For example, the entity might represent a web site.

* Attach a predefined check to the entity. For example, you could use the PING check to monitor your web site's public IP address.

* Create notifications and notification plans. A notification lets you define an action which Cloud Monitoring uses to communicate with you when a problem occurs. Notification plans allow you to organize a set of several notifications, or actions.

* Create alarms to specify which notifications get triggered.



Authenticating
===============

In order to authenticate, you need a username and API key, which you can find in the control panel by visiting the "Account Settings" page.

Once you've retrieved your details, you pass them into the client:

.. include:: samples/authentication.rst

Monitoring
===========

Create an entity
-----------------

The first thing you do to begin monitoring a resource is create an entity that represents the resource in the monitoring system. Use the following code to create the entity:

.. include:: samples/create_entity.rst

List Monitoring Zones
----------------------

Before creating a check for the new entity, choose which monitoring zones to run the check from. Cloud Monitoring is divided into different monitoring zones. You may want to have a single server monitored from several monitoring zones to reduce the risk of false alarms and check the response time from different locations around the world. To see which zones are available, consider the code sample below:

.. include:: samples/list_monitoring_zones.rst

Delete an Entity
-----------------

When you are ready to delete a monitoring entity, you may do so as follows: 

.. include:: samples/delete_entity.rst

Note: you cannot delete a monitoring entity until you have removed all its checks and alarms have been removed.

Monitoring Checks
==================

Create a Check
---------------

Any entity that you create can have many checks, each monitoring a different aspect of the entity. A basic example how to do so is presented below:

.. include:: samples/create_check.rst

List Checks
------------

If you want to list all the monitoring checks for a given entity, follow the code sample shown below:

.. include:: samples/list_checks.rst

Delete a Check
-----------------

In order to remove a check, you can proceed as shown below:

.. include:: samples/delete_check.rst

Notifications
==============

In most cases you, and perhaps several people on your team, will be interested in multiple alerts. Cloud Monitoring lets you set up notification plans that can be shared between multiple alerts.

Create Notification
--------------------

To create a notification plan, you can do as follows:

.. include:: samples/create_notification.rst

Create Alarm
--------------------

The code below shows how you can create an alarm for an entity:

.. include:: samples/create_alarm.rst

Delete Alarm
---------------

If you need to delete an alarm, do so as shown in the code samples below:

.. include:: samples/delete_alarm.rst



