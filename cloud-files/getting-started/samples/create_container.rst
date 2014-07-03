.. code-block:: csharp

  cloudFilesProvider.CreateContainer("example_container", region: "{region}");

.. code-block:: java

  cloudFilesApi.getContainerApiForRegion("{region}").create("example_container");

.. code-block:: javascript

  client.createContainer({
    name: 'example_container'
  }, function (err, container) {
    if (err) {
      // TODO handle as appropriate
      return;
    }

    // TODO use your container
  });

.. code-block:: php

  // Obtain an Object Store service object from the client.
  $objectStoreService = $client->objectStoreService(null, '{region}');

  // Create a container for your objects (also referred to as files).
  $container = $objectStoreService->createContainer('example_container');

.. code-block:: python

  container = pyrax.cloudfiles.create_container("example_container")

.. code-block:: ruby

  # Fog calls containers "directories."

  directory = @client.directories.create(:key => 'example_container')

.. code-block:: sh

  curl -i -X PUT $ENDPOINT/{containerName} \
    -H "X-Auth-Token: $TOKEN"
