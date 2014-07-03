.. code-block:: csharp

  UserName userName = new UserName("{dbUsername}");
  UserConfiguration userConfiguration = new UserConfiguration(
    userName,
    "{dbPassword}",
    new DatabaseName[] { databaseName }
  );
  await cloudDatabasesProvider.CreateUserAsync(
     databaseInstance.Id,
     userConfiguration,
     CancellationToken.None
  );

.. code-block:: java

  // Create a user by specifying a username and password, and give them access
  // to one database.
  UserApi userApi = troveApi.getUserApiForZoneAndInstance("{region}", "{instanceId}");

  userApi.create("{dbUsername}", "{dbPassword}", "sample_db");

.. code-block:: javascript

  client.createUser({
    instance: instance,
    username: {dbUsername},
    password: {dbPassword},
    databases: [ 'sample_db' ]
  }, function(err, user) {
    if (err) {
      // TODO handle err as appropriate
    }

    // TODO use your newly created user here
  });

.. code-block:: php

  $user = $instance->user();

  // Create a user by specifying a username and password, and give them access
  // to two databases.
  $user->create(array(
      'name'      => '{dbUsername}',
      'password'  => '{dbPassword}',
      'databases' => array('sample_db')
  ));

.. code-block:: python

  # Create a user by specifying the username and password, and give them
  # access to two databases.
  inst.create_user("{dbUsername}", "{dbPassword}", ["sample_db"])

.. code-block:: ruby

  # Create a user by specifying the username and password, and give them
  # access to two databases.

  instance.users.create(
    :name => '{dbUsername}',
    :password => '{dbPassword}',
    :databases => ['sample_db']
  )

.. code-block:: sh

  curl -s -X POST $ENDPOINT/instances/{instanceId}/users \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d '{
      "users": [
        {
          "databases": [
            { "name": "sample_db" }
          ],
          "name": "{dbUsername}",
          "password": "{dbPassword}"
        }
      ]
    }' | python -m json.tool
