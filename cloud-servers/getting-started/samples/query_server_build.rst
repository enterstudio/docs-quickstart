.. code-block:: csharp

.. code-block:: java

  ServerPredicates.awaitActive(serverApi).apply(serverCreated.getId())

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

  pyrax.utils.wait_for_build(server, verbose=True)

.. code-block:: ruby

  server.wait_for { active }

.. code-block:: sh

  # from resulting json below see "status"
  curl -X GET $ENDPOINT/{serverId} \
    -H "X-Auth-Token: $TOKEN" | python -m json.tool
