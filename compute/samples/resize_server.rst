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
    $curl -X PUT $endpoint/{serverId}/action \ -d \
    '{
    "resize" : {
        "flavorRef" : "{flavorRefNumber}"
     }
    }' \
    -H "X-Auth-Token: $token" | python -m json.tool