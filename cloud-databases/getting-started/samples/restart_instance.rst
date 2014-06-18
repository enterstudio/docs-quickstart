.. code-block:: csharp

  CloudDatabasesProvider cloudDatabasesProvider = new CloudDatabasesProvider(cloudIdentity, "{region}", null);
  DatabaseInstanceId databaseInstanceId = new DatabaseInstanceId("database_instance_id");
  await cloudDatabasesProvider.RestartDatabaseInstanceAsync(databaseInstanceId, AsyncCompletionOption.RequestCompleted, CancellationToken.None, null);

.. code-block:: java

  // This operation is currently not supported through the jclouds SDK.

.. code-block:: javascript

.. code-block:: php

  $instance->restart();

.. code-block:: python

  inst.restart()

.. code-block:: ruby

  instance.restart
  instance.wait_for { ready? }

.. code-block:: sh
