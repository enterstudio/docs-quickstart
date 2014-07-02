.. code-block:: csharp

  // This API call is not implemented in the .NET SDK

.. code-block:: java

  // Not currently supported by this SDK

.. code-block:: javascript

  // assuming we've already loaded the details of a snapshot into a
  // local variable named snapshot

  snapshot.name = 'new_shapshot_name';

  client.updateSnapshot(snapshot, function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  $snapshot->rename(array(
    'display_name' => 'new_snapshot_name',
    'display_description' => 'This is the new description'
  ));

.. code-block:: python

  snap.update(display_name='new_snapshot_name',
              display_description='This is the new description')

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

 $ curl -X PUT -d \
   '{
    "snapshot":{
        "display_name":"{name}",
        "display_description":"{description}"
        }
    }'\
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    $ENDPOINT/snapshots/{snapshotId} | python -m json.tool
