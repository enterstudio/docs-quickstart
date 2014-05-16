.. code-block:: csharp

.. code-block:: java

    ServerApi serverApi = novaApi.getServerApiForZone("{region}");
    serverApi.delete("{serverId}");

.. code-block:: javascript

    client.destroyServer(server, function(err) {
      // TODO handle err as appropriate
    });

.. code-block:: php

    $server->delete();

.. code-block:: python

    # Deletes server named "sacrifice"
    print("Deleting 'sacrifice' server...", end=' ')
    sacrifice.delete()
    print("  Done!")

.. code-block:: ruby

    server.destroy

.. code-block:: shell

    $ curl -X DELETE $ENDPOINT/{serverId} -H "X-Auth-TOKEN: $TOKEN"
