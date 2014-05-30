.. code-block:: csharp

.. code-block:: java

  ConnectionThrottle throttle = ConnectionThrottle.builder()
      .maxConnectionRate(10000)
      .maxConnections(5000)
      .minConnections(2)
      .rateInterval(5)
      .build();

  ConnectionApi connectionApi = clbApi.getConnectionApiForZoneAndLoadBalancer("{region}", loadBalancer.getId());
  connectionApi.createOrUpdateConnectionThrottle(throttle);

.. code-block:: javascript

.. code-block:: php

  $throttle = $loadBalancer->connectionThrottle();

  // Allow 5,000 simultaneous connections
  $throttle->create(array(
      'maxConnections' => 5000
  ));

  // Or, allow 10,000 every 5 seconds
  $throttle->create(array(
      'maxConnectionRate' => 10000,
      'rateInterval'      => 5
  ));

.. code-block:: python

  load_balancer.add_connection_throttle(maxConnectionRate=10000,
                                        maxConnections=5000,
                                        minConnections=2,
                                        rateInterval=5)

.. code-block:: ruby

  @balancer.enable_connection_throttling(5000,  # max_connections
    2,  # min_connections
    10000,  # max_connection_rate
    5)  # rate_interval

  @balancer.wait_for { ready? }

.. code-block:: sh

  curl -X PUT $ENDPOINT/loadbalancers/{loadBalancerId}/connectionthrottle \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    -d \
      '{
          "connectionThrottle": {
              "maxConnections": 5000,
              "minConnections": 2,
              "maxConnectionRate": 10000,
              "rateInterval": 5
          }
      }'
