.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  // Update object metadata.
  $object->saveMetadata(array(
      'Content-Type' => 'image/jpeg'
  ));

.. code-block:: python

  obj.set_metadata({"some-key": "another-value"})

.. code-block:: ruby

  file.metadata['some-key'] = 'another-value'
  file.save

.. code-block:: curl
    # To update object metadata:
    $ curl -i -X POST $publicUrlFiles/{containerName}/{objectName} \
        -H "X-Auth-Token: $token" \
        -H "X-Object-Meta-ImageType: png" \
        -H "X-Object-Meta-ImageSize: 400 MB"
    # NOTE: {containerName} and {objectName} are placeholders: Replace them 
    # with actual values and do not enclose them with {}.