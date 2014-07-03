.. code-block:: csharp

  cloudFilesProvider.DeleteObject("example_container", "someobject");

.. code-block:: java

  cloudFilesApi.getObjectApiForRegionAndContainer("{region}", "example_container").delete("someobject");

.. code-block:: javascript

  client.removeFile('example_container', 'someobject', function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  $object->delete();

.. code-block:: python

  obj.delete()

.. code-block:: ruby

  file.destroy

.. code-block:: sh

  curl -i -X DELETE $ENDPOINT/{containerName}/{objectName} \
    -H "X-Auth-Token: $TOKEN"
