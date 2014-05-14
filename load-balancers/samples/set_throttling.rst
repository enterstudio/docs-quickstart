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