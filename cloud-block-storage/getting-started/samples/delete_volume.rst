.. code-block:: csharp

  cbsProvider.DeleteVolume(volume.Id, "{region}");

.. code-block:: java

  volumeApi.delete(volume.getId());

.. code-block:: javascript

  client.deleteVolume(volumeId, function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  $volume->delete();

.. code-block:: python

  volume.delete()
  # Or:
  # cbs.delete(vol)

.. code-block:: ruby

  volume.destroy

.. code-block:: sh

  curl -X DELETE $ENDPOINT/volumes/{volumeId} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" | python -m json.tool
