.. code-block:: csharp


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
