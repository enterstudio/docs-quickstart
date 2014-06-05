.. code-block:: csharp

  CloudDatabasesProvider cloudDatabasesProvider = new CloudDatabasesProvider(cloudIdentity, "{region}", null);
  DatabaseInstanceId databaseInstanceId = new DatabaseInstanceId("database_instance_id");
  await cloudDatabasesProvider.ResizeDatabaseInstanceAsync(databaseInstanceId, new FlavorRef("{flavor_ref_id}"), AsyncCompletionOption.RequestCompleted, CancellationToken.None, null);

.. code-block:: java

  // This operation is currently not supported through the jclouds SDK.

.. code-block:: javascript

.. code-block:: php

  $instance->resize($flavor);

.. code-block:: python

  inst.resize(new_flavor)

.. code-block:: ruby

  instance.resize(new_flavor.id)
  instance.wait_for { ready? }

.. code-block:: sh
