.. code-block:: php

    // Get an empty LB object
    $loadBalancer = $service->loadBalancer();

    // Add the IP types that your LB will support
    $loadBalancer->addVirtualIp('PUBLIC', 4);
    $loadBalancer->addVirtualIp('PUBLIC', 6);

    // Send to the API
    $loadBalancer->create(array(
        'name'     => 'My Load Balancer',
        'port'     => 80,
        'protocol' => 'HTTP'
    ));