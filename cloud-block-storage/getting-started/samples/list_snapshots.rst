.. code-block:: csharp

   IEnumerable<Snapshot> snapshots = new CloudBlockStorageProvider("{cloudIdentity}").ListSnapshots(region: "{region}");

.. code-block:: java

  SnapshotApi snapshotApi = cinderApi.getSnapshotApiForZone("{region}");

  List<Snapshot> snapshots = snapshotApi.listInDetail().toList();

.. code-block:: javascript

  client.getSnapshots(function(err, snapshots) {
    if (err) {
      // TODO handle as appropriate
    }

    // TODO use your list of snapshots
  });

.. code-block:: php

  $snapshots = $volumeService->snapshotList(array(
    'volume_id' => $volume->id()
  ));

.. code-block:: python

  snaps = vol.list_snapshots()

.. code-block:: ruby

  @client.snapshots.all

  # To fetch only snapshots associated with a given volume:
  volume.snapshots

.. code-block:: sh

  $ curl -X GET $ENDPOINT/snapshots \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" | python -m json.tool
