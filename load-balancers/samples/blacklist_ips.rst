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