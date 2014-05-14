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