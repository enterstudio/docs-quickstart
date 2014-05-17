.. code-block:: csharp

.. code-block:: curl

   # To enable the root user for the specified database instance and
   # return the root password:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" -X POST \
      $publicUrl/instances/{instanceId}/root | python -m json.tool
   # NOTE: {instanceId} is a placeholder:
   # Replace it with an actual value and do not enclose it with {}.
   
.. code-block:: java

    InstanceApi instanceApi = troveApi.getInstanceApiForZone("{region}");

    String password = instanceApi.enableRoot("{instanceId}");

.. code-block:: javascript


.. code-block:: php

    /** @param $user OpenCloud\Database\Resource\User */
    $user = $instance->enableRootUser();

    // Store root password to your local filesystem
    file_put_contents('~/.root_mysql_pwd', $user->password);

.. code-block:: python

    inst.enable_root_user()

.. code-block:: ruby

    instance.enable_root_user

    # TODO: use the credentials from instance.root_user and instance.root_password
