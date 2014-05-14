.. code-block:: php

    $healthMonitor = $loadBalancer->healthMonitor();

    // Output the monitoring type, its delay and timeout, and the amount of
    // times it will poll the Load Balancer before deactivating
    printf(
        "Monitoring type: %s, delay: %s, timeout: %s, attempts before deactivation: %s",
        $healthMonitor->type, $healthMonitor->delay, $healthMonitor->timeout
    );