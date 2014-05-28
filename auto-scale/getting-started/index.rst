.. _quickstart:

Quickstart Guide
=================

Auto Scale
-----------

Rackspace Auto Scale is a service that lets you configure automated scaling of resources in response to an increase or decrease in overall workload based on user-defined policies. You can set up a schedule for launching Auto Scale or define an event that is triggered by Cloud Monitoring. You can also specify a minimum and maximum number of cloud servers, the amount of resources that you want to increase or decrease, and the thresholds in Cloud Monitoring that trigger the scaling activities.

To use Auto Scale, you define a scaling group consisting of cloud servers and cloud load balancers. Then you define policies, either schedule-based or monitoring-based. For monitoring-based policies, you define cloud monitoring alerts to watch the group's activity, and you define scaling rules to change the scaling group's configuration in response to alerts. For schedule-based policies, you simply set a schedule. Because you can change a scaling group's configuration in response to changing workloads, you can begin with a minimal cloud configuration and grow only when the cost of that growth is justified.

Assumptions
------------
This guide assumes the reader has working familiarity with (at the very least):
    
* Cloud Servers
* Cloud Monitoring


Concepts
===========

Scaling Groups
---------------

The scaling group is at the heart of an Auto Scale deployment. The scaling group specifies the basic elements of the Auto Scale configuration. It manages how many servers can participate in the scaling group. It also specifies information related to load balancers if your configuration uses a load balancer.

When you create a scaling group, you specify the details for the following two configurations:

* Group Configuration: Outlines the basic elements of the Auto Scale configuration. The group configuration manages how many servers can participate in the scaling group. It sets a minimum and maximum limit for the number of entities that can be used in the scaling process. It also specifies information related to load balancers

* Launch Configuration: Creates a blueprint for how new servers will be created. The launch configuration specifies what type of server image will be started on launch, what flavor the new server is, and which load balancer the new server connects to.


Webhooks and Capability URLs
-----------------------------

Auto Scale uses webhooks to initiate scaling events. A webhook is an industry-standard protocol for sending events between systems; for Auto Scale, they are used to execute policies. A webhook consists of an HTTP callback that is triggered by some user-defined event, such as an alarm that is set through Cloud Monitoring or another monitoring service.

Capability URLs are URLs that give authorization for a certain action or event. If you know the URL, you have access to it and you can use the URL to trigger a specific event. Capability URLs are usually long, and random, and cannot be guessed by a user.


Scaling Policies
-----------------

Auto Scale uses policies to define the scaling activity that will take place, as well as when and how that scaling activity will take place. Scaling policies specify how to modify the scaling group and its behavior. You can specify multiple policies to manage a scaling group.

You can create two kinds of Auto Scale policies:

* Policies that trigger Auto Scale activities through a webhook.

* Policies that trigger Auto Scale activities based on a schedule.


API Operations
===============

Authentication
----------------

Before we start working with the APIs, we first need to get our authentication token.

.. include::  samples/authentication.rst

Scaling Groups
-----------------

First, we'll create an autoscaling group.

.. include:: samples/create_scaling_group.rst

We can now list the autoscaling groups we have setup.

.. include:: samples/list_scaling_groups.rst

Or even get details of the scaling group we created.

.. include:: samples/get_scaling_group_details.rst

Let's alter the details of the scaling group.

.. include:: samples/update_scaling_group_details.rst

Look into the state of the autoscaling group.

.. include:: samples/get_scaling_group_state.rst

Finally, delete the autoscaling group.

.. include:: samples/delete_scaling_group.rst


Policies
----------

Let's create an autoscale policy that will

* Add one server
* Only allow another scaling action to happen after a 360 second cool down

.. include:: samples/create_scaling_policy.rst

Then, to list all autoscaling policies in a region you can do as follows:

.. include:: samples/list_scaling_policies.rst

Alternatively, the code samples below show how to go about if you want to inspect details of a specific autoscaling policy:

.. include:: samples/get_scaling_policy_details.rst

If you want to alter details for a policy:

.. include:: samples/update_scaling_policy.rst

To execute a particular autoscaling policy:

.. include:: samples/execute_scaling_policy.rst

Finally, if you want to delete an autoscaling policy:

.. include:: samples/delete_scaling_policy.rst


Webhooks
---------

To trigger our autoscale actions, we can create a webhook:

.. include:: samples/create_scaling_webhook.rst

Then we'll inspect the autoscaling Webhook details:

.. include:: samples/get_scaling_webhook_details.rst

We could also list all available autoscaling Webhooks in a particular region:

.. include:: samples/list_scaling_webhooks.rst

Now we can alter details about the webhook:

.. include:: samples/update_scaling_webhook.rst

Finally, delete the webhook if we don't need it:

.. include:: samples/delete_scaling_webhook.rst
