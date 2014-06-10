.. code-block:: csharp

.. code-block:: java
  HealthMonitor healthMonitor = HealthMonitor.builder()
      .type(HealthMonitor.Type.CONNECT)
      .delay(3599)
      .timeout(30)
      .attemptsBeforeDeactivation(2)
      .build();

  clbApi.getHealthMonitorApiForZoneAndLoadBalancer("{region}", loadBalancer.getId())
      .createOrUpdate(healthMonitor);

.. code-block:: javascript

  // using our previously created lb

  lb.updateHealthMonitor({
    type: 'CONNECT',
    attemptsBeforeDeactivation: 2,
    delay: 3599,
    timeout: 30
  }, function (err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

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
