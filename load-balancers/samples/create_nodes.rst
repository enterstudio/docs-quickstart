.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  // Create an empty Load Balancer object
  $loadBalancer = $loadBalancerService->loadBalancer();

  // Create first node
  $serverOneNode = $loadBalancer->node(array(
      'address'   => $serverOne->addresses->private[0]->addr,
      'port'      => 8080,
      'condition' => 'ENABLED'
  ));

  // Create second node
  $serverTwoNode = $loadBalancer->node(array(
      'address'   => $serverTwo->addresses->private[0]->addr,
      'port'      => 8080,
      'condition' => 'ENABLED'
  ));

.. code-block:: python

.. code-block:: ruby

  @balancer = @client.load_balancers.create(
    :name => 'balanced',
    :protocol => 'HTTP',
    :port => 8080,
    :virtual_ips => [{ :type => 'PUBLIC' }],
    :nodes => []
  )
  @balancer.wait_for { ready? }

  # Create the nodes
  @nodes = [@server0, @server1].map do |server|
    @balancer.nodes.create(
      :address => server.addresses['private'][0]['addr'],
      :port => 8080,
      :condition => 'ENABLED'
    )
  end
