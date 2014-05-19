.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    // To create a snapshot for a volume, the volume should be detached from
    // any server. You must supply a name for the snapshot, and may provide
    // an optional description.

    $snapshot = $volumeService->snapshot();
    $snapshot->create(array(
        'display_name' => 'name-here',
        'display_description' => 'This is the description',
        'volume_id' => $volume->id()
    ));

.. code-block:: python

  # To create a snapshot for a volume, the volume should be detached from
  # any server. You must supply a name for the snapshot, and may provide
  # an optional description.

  snap = vol.create_snapshot('name-here', 'This is the description')

.. code-block:: ruby

  # To create a snapshot for a volume, the volume should be detached from
  # any server. You must supply a name for the snapshot, and may provide
  # an optional description.

  snapshot = volume.create_snapshot(
    :display_name => 'name-here',
    :display_description => 'This is the description'
  )
