.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  client.removeFile('sample-container-test', 'somefile.txt', function(err) {
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

.. code-block:: curl
    # To delete an object:
    $ curl -i -X DELETE $publicUrlFiles/{containerName}/{objectName} \
        -H "X-Auth-Token: $token"
    # NOTE: {containerName} and {objectName} are placeholders: Replace them 
    # with actual values and do not enclose them with {}.