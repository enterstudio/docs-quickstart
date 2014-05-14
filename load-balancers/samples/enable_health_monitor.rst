.. code-block:: php

    $healthMonitor = $loadBalancer->healthMonitor();
    $healthMonitor->update(array(
        'delay' => 20
    ));