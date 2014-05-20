.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  // To check whether caching is enabled
  if (true === $loadBalancer->hasContentCaching()) {
      // it does
  }

  // To enable caching
  $loadBalancer->enableContentCaching(true);

  // To disable caching
  $loadBalancer->enableContentCaching(false);

.. code-block:: python

.. code-block:: ruby

  # To check whether or not content caching is enabled
  @balancer.content_caching

  # To enable content caching
  @balancer.enable_content_caching
  @balancer.wait_for { ready? }

  # To disable caching
  @balancer.disable_content_caching
  @balancer.wait_for { ready? }

.. code-block:: shell
