.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $snapshot = $volumeService->snapshot({snap_id});

.. code-block:: python

    snap = cbs.get_snapshot({snap_id})

.. code-block:: ruby

  @client.snapshots.get('{snapshotId}')

 .. code-block:: shell

    $ curl -X GET $ENDPOINT/snapshots/{snapshotId}
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" | python -m json.tool 
