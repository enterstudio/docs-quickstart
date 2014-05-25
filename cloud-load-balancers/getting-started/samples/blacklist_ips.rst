.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  // Example 1: Blacklist a specific IP
  $accessItem = $loadBalancer->access();
  $accessItem->create(array(
      'type'    => 'DENY',
      'address' => '206.160.165.0/24'
  ));

  // Example 2: Only allow access to 1 IP, and blacklist everything else
  $whitelistedItem = $loadBalancer->access();
  $whitelistedItem->create(array(
      'type'    => 'ALLOW',
      'address' => '206.160.165.0/24'
  ));

  $blacklistedItems = $loadBalancer->access();
  $blacklistedItems->create(array(
      'type'    => 'DENY',
      'address' => '0.0.0.0/0'
  ));

.. code-block:: python

  load_balancer.add_access_list([
      {"type": 'DENY', "address": "206.160.165.0/24"},
      {"type": 'ALLOW', "address": "206.160.166.0/24"},
      {"type": 'DENY', "address": "0.0.0.0/0"}
  ])

.. code-block:: ruby

  # Example 1: Blacklist a specific IP

  @balancer.access_rules.create(
    :type => 'DENY',
    :address => '206.160.165.0/24'
  )
  @balancer.wait_for { ready? }

  # Example 2: Allow access to 1 IP, and blacklist everything else
  @balancer.access_rules.create(
    :type => 'ALLOW',
    :address => '206.160.166.0/24'
  )
  @balancer.wait_for { ready? }

  @balancer.access_rules.create(
    :type => 'DENY',
    :address => '0.0.0.0/0'
  )
  @balancer.wait_for { ready? }

.. code-block:: sh

  # Example 1: Blacklist a specific IP

  curl -X POST $ENDPOINT/{loadBalancerId}/accesslist \
    -H "X-Auth-Token: $TOKEN" \
    -H 'Content-Type: application/json' \
    -d \
      '{
          "accessList": [
              {
                  "address" : "206.160.165.0/24",
                  "type": "DENY"
              }
          ]
      }'

  # Example 2: Allow access to 1 IP, and blacklist everything else
  curl -X POST $ENDPOINT/loadbalancers/{loadBalancerId}/accesslist \
    -H "X-Auth-Token: $TOKEN" \
    -H 'Content-Type: application/json' \
    -d \
      '{
          "accessList": [
              {
                  "address" : "206.160.166.0/24",
                  "type": "ALLOW"
              },
              {
                  "address" : "0.0.0.0/0",
                  "type": "DENY"
              }
          ]
      }'
