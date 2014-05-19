.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    // To create the volume, specify a name and size (in GB). You may optionally
    // specify a volume type, which is either 'SSD' (faster, more expensive), or
    // 'SATA' (more affordable). SATA is the default if you omit this.
    $volume = $volumeService->volume();
    $volume->create(array(
        'display_name' => '{name}',
        'size' => {size_in_GB},
        'volume_type' => '{volume_type}'
    ));

.. code-block:: python

    # To create the volume, specify a name and size (in GB). You may optionally
    # specify a volume type, which is either 'SSD' (faster, more expensive), or
    # 'SATA' (more affordable). SATA is the default if you omit this.
    vol = cbs.create({name}, {size_in_GB}, {volume_type})

.. code-block:: ruby

  # The :size parameter is specified in GB, with a minimum of 100GB.

  volume = @client.volumes.create(:size => '100')
  volume.wait_for { ready? }

.. code-block:: shell

  $ curl -X POST -d \
    '{
    "volume": {
        "display_name": "{name}",
        "size": 100
     }
    }'\    
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    $ENDPOINT/volumes | python -m json.tool
