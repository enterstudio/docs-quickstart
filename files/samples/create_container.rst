.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  client.createContainer({
    name: 'sample-container-test'
  }, function (err, container) {
    if (err) {
      // TODO handle as appropriate
      return;
    }

    // TODO use your container
  });

.. code-block:: php

  // Obtain an Object Store service object from the client.
  $region = 'DFW';
  $objectStoreService = $client->objectStoreService(null, $region);

  // Create a container for your objects (also referred to as files).
  $container = $objectStoreService->createContainer('gallery');

.. code-block:: python

  container = pyrax.cloudfiles.create_container("gallery")

.. code-block:: ruby

  # Fog calls containers "directories."

  directory = @client.directories.create(:key => 'sample-container-test')
  
.. code-block:: curl
    # To create a storage container:
    $ curl -i -X PUT $publicUrlFiles/{containerName} \
        -H "X-Auth-TOKEN: $TOKEN" 
    # NOTE: {containerName} is a placeholder: Replace it with 
    # an actual value and do not enclose it with {}.
