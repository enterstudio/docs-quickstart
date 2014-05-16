.. code-block:: csharp

.. code-block:: java

    ServerApi serverApi = novaApi.getServerApiForZone("{region}");
    serverApi.resize("{serverId}", "{flavorId}");

.. code-block:: javascript

.. code-block:: php

    // Load your new flavor
    $newFlavor = $compute->flavor('{newFlavorId}');

    $server->resize($newFlavor);

.. code-block:: python

.. code-block:: ruby

.. .. code-block:: shell

    #first you should get the flavor ref number from flavor listing
    $curl -X PUT $ENDPOINT/{serverId}/action \ -d \
      '{
      "resize" : {
          "flavorRef" : "{flavorRefNumber}"
       }
      }' \
      -H "X-Auth-TOKEN: $TOKEN" | python -m json.tool