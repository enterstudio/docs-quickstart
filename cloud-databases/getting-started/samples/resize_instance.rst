.. code-block:: csharp

  DatabaseInstanceId databaseInstanceId = new DatabaseInstanceId("database_instance_id");
  await cloudDatabasesProvider.ResizeDatabaseInstanceAsync(databaseInstanceId, new FlavorRef("{flavor_ref_id}"), AsyncCompletionOption.RequestCompleted, CancellationToken.None, null);

.. code-block:: java

  // Not currently supported by this SDK

.. code-block:: javascript

  client.setFlavor(instance, {newFlavor}, function(err) {
    if (err) {
      // TODO handle err as appropriate
    }
  });

.. code-block:: php

  $instance->resize($flavor);

.. code-block:: python

  inst.resize(new_flavor)

.. code-block:: ruby

  instance.resize(new_flavor.id)
  instance.wait_for { ready? }

.. code-block:: sh

  curl -s -X POST $ENDPOINT/instances/{instanceId}/action \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d "{
      \"resize\": { \"flavorRef\": \"$NEW_FLAVOR_REF\" }
    }" | python -m json.tool
