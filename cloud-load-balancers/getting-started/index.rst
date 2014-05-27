===================================
Getting Started with Load Balancers
===================================

The Rackspace Load Balancers service provides a means to protect your infrastructure
by distributing traffic efficiently.

Authenticating
==============

In order to work with the Load Balancer service, you must authenticate:

.. include:: samples/authentication.rst

Setting up your Load Balancer
=============================

Create a Load Balancer
----------------------

When creating a load balancer, there are a few mandatory parameters that you need
to provide. You will need to specify a **name**, a **protocol** (e.g. HTTP, FTP,
SMTP) and the types of IP you want to use (v4 or v6). Here is an example:

.. include:: samples/create_lb.rst

Once this operation is executed, the API will asynchronously provision a Load
Balancer based on your configuration. Some SDKs allow you to query its progress:

.. include:: samples/query_lb_progress.rst


Select the servers you want as nodes
------------------------------------

In order for a load balancer to distribute traffic, it needs to be aware of the
servers or databases you want guarded - these are known as Nodes.

.. include:: samples/select_servers.rst

The above sample retrieves two Cloud Servers using their unique IDs. If you
do not know their IDs, you can follow the steps outlined in the Compute Getting
Started Guide for retrieving servers based on arbitrary properties.

Now you have your servers, you can create your nodes and add them to the load
balancer:

.. include:: samples/create_nodes.rst

Monitoring the health of your nodes
-----------------------------------

The load balancing service includes a health monitor that periodically checks
your nodes to ensure they are responding correctly. If a node is not responding,
it is removed from rotation until the health monitor determines that it is
functional. In addition to periodic checking, a check is performed against every
node when added to your Load Balancer - ensuring that the Node can safely service traffic.

To enable health monitoring on your Load Balancer, you'll need to set:

* Type - ``CONNECT`` is used to monitor connections
* Delay - Minimum number of seconds to wait before executing the monitor
* Timeout - Maximum duration in seconds to wait for a connection establishment before timing out
* Attempts before deactivation - Number of monitor failures to tolerate before removing a node from rotation

.. include:: samples/enable_health_monitor.rst

To view the status of a health monitor:

.. include:: samples/query_health_monitor.rst

Please be aware that only one health monitor is allowed to be enabled on a load
balancer at a time.

Connection throttling
=====================

The connection throttling feature imposes limits on the number of connections per IP address to help mitigate malicious or abusive traffic to your applications. You can set the:

* Max connection rate - Maximum connections from a single IP within the supplied rate interval (frequency in seconds)
* Max connections - Maximum simultaneous connections to allow from a single IP within the rate interval
* Min connections - Minimum amount of connections per IP before doing any throttling

.. include:: samples/set_throttling.rst

Blacklisting IP addresses
=========================

Your Access List allows fine-grained network access controls to be applied to a
Load Balancer. A single IP address, multiple IP addresses,￼or entire network
subnets can be added.

Items that are configured with the ``ALLOW`` type will take precedence over all
other traffic, and items with the ``DENY`` type will have their traffic rejected.

.. include:: samples/blacklist_ips.rst

Caching content for performance
===============================

When content caching is enabled, recently-accessed files are stored on the load
balancer for easy retrieval by web clients. Content caching improves the
performance of high traffic web sites by temporarily storing data that was
recently accessed. While it's cached, requests for that data will be served by
the load balancer, which in turn reduces load off the back end nodes. The result
is improved response times for those requests and less load on the web server.

.. include:: samples/enable_content_caching.rst

Using error pages
=================

An error page is the HTML file that is shown to your users when accessing a
load balancer node that is offline or otherwise unavailable. By default, every
provisioned load balancer is configured with a default error page - however it
is possible to create a custom one for Load Balancers that use the HTTP protocol:

.. include:: samples/set_custom_error_page.rst
