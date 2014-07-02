.. code-block:: csharp

  // To restore a database, you must first use an existing backup to
  // create a Restore Point, then use that Restore Point to create
  // a database instance.
  DatabaseInstanceId databaseInstanceId = new DatabaseInstanceId("{database_instance_id}");
  BackupId backupId = new BackupId("{backup_id}");
  RestorePoint restorePoint = new RestorePoint(backupId);
  FlavorRef flavorRef = new FlavorRef("{flavor_ref_id}");
  DatabaseVolumeConfiguration databaseVolumeConfiguration = new DatabaseVolumeConfiguration({database_volume_configuration_id});
  DatabaseInstanceConfiguration databaseInstanceConfiguration = new DatabaseInstanceConfiguration(flavorRef, databaseVolumeConfiguration, "{instance_name}",restorePoint);
  DatabaseInstance databaseInstance = await cloudDatabasesProvider.CreateDatabaseInstanceAsync(databaseInstanceConfiguration, AsyncCompletionOption.RequestCompleted, CancellationToken.None, null);

  // This operation is currently not supported through the .NET SDK.

.. code-block:: java

  // This operation is currently not supported through the jclouds SDK.

.. code-block:: javascript

  // This operation is currently not supported with pkgcloud.

.. code-block:: php

.. code-block:: python

  # When restoring from a backup, you must supply a backup (either the backup
  # object or its ID), a name for the new instance to be created from the
  # backup, as well as a flavor and size (in GB) for the instance.
  new_inst = cdb.restore_backup(backup, "new_name", flavor=flavor,
                                volume=20)

.. code-block:: ruby

  # This operation is currently not supported through the fog SDK.

.. code-block:: sh

  curl -s -X POST $ENDPOINT/instances \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d "{
      \"instance\": {
        \"name\": \"new_name\",
        \"flavorRef\": \"$FLAVOR_REF\",
        \"volume\": { \"size\": 20 },
        \"restorePoint\": {
          \"backupRef\": \"$BACKUP_ID\"
        }
      }
    }" | python -m json.tool
