.. code-block:: csharp

  Snapshot snapshot = cbsProvider.CreateSnapshot(volume.Id,
    displayName: "Some Snapshot",
    displayDescription: "This is the description",
    region: "{region}"
  );

.. code-block:: java

  // Get the volume to snapshot
  Volume volume = volumeApi.get("{volumeId}")

  CreateSnapshotOptions options = CreateSnapshotOptions.Builder
      .name("Some Snapshot")
      .description("This is the description");

  Snapshot snapshot = snapshotApi.create(volume.getId(), options);

.. code-block:: javascript

  // To create a snapshot for a volume, the volume should be detached from
  // any server. You must supply a name for the snapshot, and may provide
  // an optional description.

  client.createSnapshot({
    name: 'Some Snapshot',
    description: 'This is the description',
    volumeId: '{volumeId}'
  }, function(err, snapshot) {
    if (err) {
      // TODO handle as appropriate
    }

    // TODO use your newly created snapshot
  });

.. code-block:: php

  // To create a snapshot for a volume, the volume should be detached from
  // any server. You must supply a name for the snapshot, and may provide
  // an optional description.

  $snapshot = $volumeService->snapshot();
  $snapshot->create(array(
      'display_name' => 'Some Snapshot',
      'display_description' => 'This is the description',
      'volume_id' => $volume->id()
  ));

.. code-block:: python

  # To create a snapshot for a volume, the volume should be detached from
  # any server. You must supply a name for the snapshot, and may provide
  # an optional description.

  snapshot = vol.create_snapshot('Some Snapshot', 'This is the description')

.. code-block:: ruby

  # To create a snapshot for a volume, the volume should be detached from
  # any server. You must supply a name for the snapshot, and may provide
  # an optional description.

  snapshot = volume.create_snapshot(
    :display_name => 'Some Snapshot',
    :display_description => 'This is the description'
  )

.. code-block:: sh

  curl -X POST $ENDPOINT/snapshots \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    -d '{
      "snapshot": {
        "display_name": "Some Snapshot",
        "display_description": "This is the description",
        "volume_id": "{volumeId}"
      }
    }' | python -m json.tool
