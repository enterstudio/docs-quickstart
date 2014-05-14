.. code-block:: php

    // To check whether caching is enabled
    if (true === $loadBalancer->hasContentCaching()) {
        // it does
    }

    // To enable caching
    $loadBalancer->enableContentCaching(true);

    // To disable caching
    $loadBalancer->enableContentCaching(false);