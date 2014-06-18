.. code-block:: csharp

.. code-block:: curl

   # To create a database:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" \
      -H "Content-Type: application/json" -X POST \
      -d '{"databases": [{"character_set": "utf8","collate": "utf8_general_ci",
         "name": "testingdb"},{"name": "anotherdb"},{"name": "oneMoreDB"}]}' \
      $publicUrl/instances/{instanceId}/databases | python -m json.tool
   # NOTE: {instanceId} is a placeholder:
   # Replace it with an actual value and do not enclose it with {}.

.. code-block:: java

    DatabaseApi databaseApi = troveApi.getDatabaseApiForZoneAndInstance("{region}", "{instanceId}";

    boolean result = databaseApi.create("{dbName}");

.. code-block:: javascript


.. code-block:: php

    $db = $instance->database();

    $db->create(array(
        'name' => 'wordpress'
    ));

.. code-block:: python

    inst.create_database("sample_db")

.. code-block:: ruby

    database = instance.databases.create(:name => 'sample_db')
