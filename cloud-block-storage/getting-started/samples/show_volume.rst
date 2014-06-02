.. code-block:: csharp

  Volume volume = new CloudBlockStorageProvider({cloudIdentity}).ShowVolume("{volumeId}", region: "{region}");

.. code-block:: java

  Volume volume = volumeApi.get("{volumeId}");

.. code-block:: javascript

.. code-block:: php

  $volume = $volumeService->volume('{volumeId}');

.. code-block:: python

  volume = cbs.get('{volumeId}')

.. code-block:: ruby

  volume = @client.volumes.get('{volumeId}')

 .. code-block:: sh

    $ curl -X GET $ENDPOINT/volumes/{volumeId}
      -H "X-Auth-Token: $TOKEN" \
      -H "Content-Type: application/json" | python -m json.tool 
