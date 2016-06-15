.. code-block:: csharp

  Server server = cloudServersProvider.WaitForServerActive(newServer.Id);

.. code-block:: go

  err := servers.WaitForStatus(serviceClient, server.ID, "ACTIVE", 600)

.. code-block:: java

  ServerApi serverApi = novaApi.getServerApi("{region}");

  ServerPredicates.awaitActive(serverApi).apply("{serverId}")

.. code-block:: javascript

  server.setWait({ status: server.STATUS.running }, 6000, function(err) {
    if (err) {
      // TODO handle err as appropriate
    }

    // TODO continue after status is running
  });

.. code-block:: php

  $server->waitFor('ACTIVE', 600);

.. code-block:: python

  pyrax.utils.wait_for_build(server, verbose=True)

.. code-block:: ruby

  server.wait_for { active }

.. code-block:: sh

  # from resulting json below see "status"
  curl -X GET $ENDPOINT/servers/$SERVER_ID \
    -H "X-Auth-Token: $TOKEN" | python -m json.tool
