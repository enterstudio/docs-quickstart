.. code-block:: csharp

.. code-block:: curl

   # To asynchronously create a backup for a specified database instance:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" \
      -H "Content-Type: application/json" -X POST \
      -d '{"backup": {"description": "My Backup","instance": "d4603f69-ec7e-4e9b-803f-600b9205576f","name": "snapshot"}}' \
      $publicUrl/backups | python -m json.tool
   
.. code-block:: java

    // This operation is currently not supported through the jclouds SDK.

.. code-block:: javascript


.. code-block:: php


.. code-block:: python

    backup = inst.create_backup("backup_name")

.. code-block:: ruby

    # N/A
