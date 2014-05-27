.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  $healthMonitor = $loadBalancer->healthMonitor();
  $healthMonitor->update(array(
      'delay' => 20
  ));

.. code-block:: python

  load_balancer.add_health_monitor(type="CONNECT", delay=10, timeout=10,
                                   attemptsBeforeDeactivation=3)

.. code-block:: ruby

  @balancer.enable_health_monitor('CONNECT', 10, 10, 3)
  @balancer.wait_for { ready? }

.. code-block:: sh

  curl -X PUT $ENDPOINT/loadbalancers/{loadBalancerId}/healthmonitor \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    -d \
      '{
          "healthMonitor": {
              "type": "CONNECT",
              "delay": 10,
              "timeout": 10,
              "attemptsBeforeDeactivation": 3
          }
      }'
