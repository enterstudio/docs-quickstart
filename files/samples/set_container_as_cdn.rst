.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  container.enableCdn(function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  // Enable CDN for the container.
  $container->enableCdn();

.. code-block:: python

  container.make_public()

.. code-block:: ruby

  directory.public = true
  directory.save
  
.. code-block:: curl
    # To CDN-enable a storage container:
    $ curl -i -X PUT $publicUrlCDN/{containerName} /
        -H "X-Auth-TOKEN: $TOKEN" \
        -H "X-CDN-Enabled: True" \
        -H "X-TTL: 604800"
    # NOTE: {containerName} is a placeholder: Replace it with 
    # an actual value and do not enclose it with {}.
