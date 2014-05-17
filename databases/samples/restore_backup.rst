.. code-block:: csharp

.. code-block:: curl

   # To asynchronously create a backup for a specified database instance:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" \
      -H "Content-Type: application/json" -X POST \
      -d '{"instance": {"flavorRef": 1,"name": "json_restore","restorePoint": {
      "backupRef": {backupId}"},"volume": {"size": 2}}}' \
      $publicUrl/instances | python -m json.tool
      # NOTE: {backId} is a placeholder:
      # Replace it with an actual value and do not enclose it with {}.
      
.. code-block:: java

    // Currently not supported

.. code-block:: javascript


.. code-block:: php


.. code-block:: python

    # When restoring from a backup, you must supply a backup (either the backup
    # object or its ID), a name for the new instance to be created from the
    # backup, as well as a flavor and size (in GB) for the instance.
    new_inst = cdb.restore_backup(backup, "new_name", flavor=flavor,
            volume=20GB)

.. code-block:: ruby

    # N/A
