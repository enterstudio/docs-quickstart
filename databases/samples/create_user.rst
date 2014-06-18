.. code-block:: csharp

.. code-block:: curl

   # To create a user for a specified database instance:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" \
      -H "Content-Type: application/json" -X POST \
      -d '{"users": [{"databases": [{"name": "databaseA"}],"name": "dbuser1","password": "password"}]}' \
      $publicUrl/instances/{instanceId}/users | python -m json.tool
   # NOTE: {instanceId} is a placeholder:
   # Replace it with an actual value and do not enclose it with {}.

.. code-block:: java

    UserApi userApi = troveApi.getUserApiForZoneAndInstance("{region}", "{instanceId}");

    boolean result = userApi.create("{dbUsername}", "{dbPassword}", "{dbName}");

.. code-block:: javascript


.. code-block:: php

    $user = $instance->user();

    // Create user and assign them to some DBs
    $user->create(array(
        'name'      => '{dbUsername}',
        'password'  => '{dbPassword}',
        'databases' => array('{dbName1}', '{dbName2}')
    ));

.. code-block:: python

    # Create a user by specifying the username and password, and give them
    # access to two databases.
    inst.create_user("{dbUsername}", "{dbPassword}", ["{dbName1}", "{dbName2}"])

.. code-block:: ruby

    # Create a user by specifying the username and password, and give them
    # access to two databases.

    instance.users.create(
      :name => '{dbUsername}',
      :password => '{dbPassword}',
      :databases => ['{dbName1}', '{dbName2}']
    )
