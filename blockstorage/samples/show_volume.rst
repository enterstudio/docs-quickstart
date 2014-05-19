.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $volume = $volumeService->volume(getenv('RAX_VOLUME_ID'));

.. code-block:: python

    vol = cbs.get({volume_id})

.. code-block:: ruby

  volume = @client.volumes.get('{volumeId}')

 .. code-block:: shell

    $ curl -X GET $ENDPOINT/volumes/{volumeId}
      -H "X-Auth-Token: $TOKEN" \
      -H "Content-Type: application/json" | python -m json.tool 