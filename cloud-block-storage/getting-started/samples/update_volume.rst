.. code-block:: csharp

  // This API call is not implemented in the .NET SDK

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

  // assuming we've already loaded the details of a volume into a
  // local variable named volume

  volume.name = 'new_volume_name';

  client.updateVolume(volume, function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  $volume->rename(array(
      'display_name' => 'new_volume_name',
      'display_description' => 'This is the new volume description'
  ));

.. code-block:: python

  vol.update(display_name='new_volume_name',
             display_description='This is the new volume description')

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

 $ curl -X PUT -d \
   '{
    "snapshot":{
        "display_name":"{name}",
        "display_description":"{description}"
        }
    }'\
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    $ENDPOINT/volumes/{volumeId} | python -m json.tool
