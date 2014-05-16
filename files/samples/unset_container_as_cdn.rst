.. code-block:: javascript

  container.disableCdn(function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  // Disable CDN for the container.
  $container->disableCdn();

.. code-block:: python

  container.make_private()

.. code-block:: ruby

  directory.public = false
  directory.save
  
.. code-block:: curl
    # To disable CDN for a container:  
    $ curl -i -X POST $publicUrlCDN/{containerName} /
      -H "X-Auth-TOKEN: $TOKEN" \
      -H "X-CDN-Enabled: False"
    # NOTE: {containerName} is a placeholder: Replace it with 
    # an actual value and do not enclose it with {}.
