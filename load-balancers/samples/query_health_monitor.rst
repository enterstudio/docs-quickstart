.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  $healthMonitor = $loadBalancer->healthMonitor();

  // Output the monitoring type, its delay and timeout, and the amount of
  // times it will poll the Load Balancer before deactivating
  printf(
      "Monitoring type: %s, delay: %s, timeout: %s, attempts before deactivation: %s",
      $healthMonitor->type, $healthMonitor->delay, $healthMonitor->timeout
  );

.. code-block:: python

.. code-block:: ruby

  # Arguments, in order:
  #
  #  type: Type of the health monitor. Must be 'CONNECT' to monitor connections.
  #  delay: Minimum number of seconds to wait before executing the monitor, between
  #         1 and 3600.
  #  timeout: Maximum number of seconds to wait for a connection to be established
  #           before timing out, between 1 and 300.
  #  attempts_before_deactivation: Number of monitor failures to tolerate before
  #                                removing a node from rotation. Between 1 and 10.
  @balancer.enable_health_monitor('CONNECT', 10, 10, 3)
