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

  # Create the nodes
  @server_one_node = @balancer.nodes.create(
    :address => @server_one.addresses['private'][0]['addr'],
    :port => 8080,
    :condition => 'ENABLED'
  )

  @server_two_node = @balancer.nodes.create(
    :address => @server_two.addresses['private'][0]['addr'],
    :port => 8080,
    :condition => 'ENABLED'
  )
