.. code-block:: csharp

  Snapshot snapshot = new CloudBlockStorageProvider({cloudIdentity}).ShowSnapshot("{snapshotId}", "{region}");
			
.. code-block:: java

  Snapshot snapshot = snapshotApi.get("{snapshotId}");

.. code-block:: javascript

.. code-block:: php

  $snapshot = $volumeService->snapshot('{snapshotId}');

.. code-block:: python

  snapshot = cbs.get_snapshot('{snapshotId}')

.. code-block:: ruby

  snapshot @client.snapshots.get('{snapshotId}')

 .. code-block:: sh

    $ curl -X GET $ENDPOINT/snapshots/{snapshotId}
      -H "X-Auth-Token: $TOKEN" \
      -H "Content-Type: application/json" | python -m json.tool 