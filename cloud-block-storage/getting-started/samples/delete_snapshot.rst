.. code-block:: csharp

  cbsProvider.DeleteSnapshot(snapshot.Id, "{region}");

.. code-block:: java

  snapshotApi.delete("{snapshotId}");

.. code-block:: javascript

  client.deleteSnapshot(snapshotId, function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  $snapshot->delete();

.. code-block:: python

  snapshot.delete()
  # Or:
  # cbs.delete_snapshot('{snapshotId}')

.. code-block:: ruby

  snapshot.destroy

.. code-block:: sh

  curl -X DELETE $ENDPOINT/snapshots/{snapshotId} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" | python -m json.tool
