.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  // Create the first node
  $serverOneNode = $loadBalancer->node(array(
      'address'   => $serverOne->addresses->private[0]->addr,
      'port'      => 8080,
      'condition' => 'ENABLED'
  ));

  // Create the second node
  $serverTwoNode = $loadBalancer->node(array(
      'address'   => $serverTwo->addresses->private[0]->addr,
      'port'      => 8080,
      'condition' => 'ENABLED'
  ));

.. code-block:: python

.. code-block:: ruby

  @server_one_node = @balancer.nodes.create(
    :address => @server_one.private_ip_address
    :port => 8080,
    :condition => 'ENABLED'
  )
  @balancer.wait_for { ready? }

  @server_two_node = @balancer.nodes.create(
    :address => @server_two.private_ip_address
    :port => 8080,
    :condition => 'ENABLED'
  )
  @balancer.wait_for { ready? }
