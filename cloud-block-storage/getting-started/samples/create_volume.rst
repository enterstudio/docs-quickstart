.. code-block:: csharp

  volume = cbsProvider.CreateVolume(
    size: 100,
    displayDescription: "This is the description",
    displayName: "Some Volume",
    region: "{region}"
  );

.. code-block:: java

  CreateVolumeOptions options = CreateVolumeOptions.Builder
        .name("Some Volume")
        .volumeType("SATA");

  Volume volume = volumeApi.create(100, options);

.. code-block:: javascript

  // To create the volume, specify a name and size (in GB, with a miminum of
  // 100GB). You may optionally specify a volume type, which is either 'SSD'
  // (faster, more expensive), or 'SATA' (more affordable). SATA is the
  // default if you omit this.

  client.createVolume({
    name: 'Some Volume',
    volumeType: 'SATA',
    size: 100
  }, function(err, volume) {
    if (err) {
      // TODO handle as appropriate
    }

    // TODO use your newly created volume
  });

.. code-block:: php

  // To create the volume, specify a name and size (in GB, with a miminum of
  // 100GB). You may optionally specify a volume type, which is either 'SSD'
  // (faster, more expensive), or 'SATA' (more affordable). SATA is the
  // default if you omit this.

  $volume = $volumeService->volume();
  $volume->create(array(
      'display_name' => 'Some Volume',
      'size' => 100,
      'volume_type' => 'SATA'
  ));

.. code-block:: python

  # To create the volume, specify a name and size (in GB, minimum 100GB). You
  # may optionally specify a volume type, which is either 'SSD' (faster, more
  # expensive), or 'SATA' (more affordable). SATA is the default if you omit
  # this.

  volume = cbs.create('Some Volume', 100, 'SATA')

.. code-block:: ruby

  # The :size parameter is specified in GB, with a minimum of 100GB.
  # The :volume_type parameter may be either 'SSD' (faster, more expensive), or
  # 'SATA' (more affordable). SATA is the default it you omit this.
  volume = @client.volumes.create(
    :display_name => 'Some Volume',
    :size => '100',
    :volume_type => 'SATA'
  )
  volume.wait_for { ready? }

.. code-block:: sh

  curl -X POST $ENDPOINT/volumes
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    -d '{
    "volume": {
        "display_name": "Some Volume",
        "size": 100
     }
    }' | python -m json.tool
