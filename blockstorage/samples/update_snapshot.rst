.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $snapshot->rename(array(
        'display_name' => '{new_display_name}',
        'display_description' => '{new_display_description}'
    ));
    
.. code-block:: python

   snap.update(display_name={new_display_name},
        display_description={new_display_description})

.. code-block:: ruby

  # N/A

.. code-block:: shell

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