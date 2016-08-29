.. code-block:: csharp

  cloudFilesProvider.CreateObjectFromFile("{container_name}", "{path_to_file}", "{subdirectories}/{object_name}");

.. code-block:: go

  _, err := objects.Create(
    serviceClient,
    "{containerName}",
    "{subdirectories}/{objectName}",
    reader,
    nil,
  ).ExtractHeader()

.. code-block:: java

  objectApi.put("{subdirectories}/{objectName}", filePayload);

.. code-block:: javascript

  var dest = client.upload({
    container: 'sample-container-test',
    remote: '{subdirectories}/{objectName}'
  });

.. code-block:: php

  $object = $container->uploadObject('{subdirectories}/{object_name}', $handle);

.. code-block:: python

  obj = container.store_object("{subdirectories}/{object_name}", data)

.. code-block:: ruby

  file = directory.files.create(
    :key => '{subdirectories}/{object_name}',
    :body => 'Rackspace is awesome!'
  )

.. code-block:: sh

  curl -i -X PUT $ENDPOINT/{containerName}/{subdirectories}/{objectName} /
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: image/jpeg" \
    -H "Content-Length: 0"
