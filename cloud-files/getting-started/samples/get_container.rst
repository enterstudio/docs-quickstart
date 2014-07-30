.. code-block:: csharp

.. code-block:: java

  ContainerApi containerApi = cloudFilesApi.getContainerApiForRegion("{region}");

  Container container = containerApi.get("{containerName}");

.. code-block:: javascript

.. code-block:: php

  $container = $objectStoreService->getContainer('{containerName}');

.. code-block:: python

.. code-block:: ruby

  directory = @client.directories.get('{containerName}')

.. code-block:: sh

  curl -i -X GET $ENDPOINT/{containerName} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json"
