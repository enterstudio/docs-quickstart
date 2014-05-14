.. code-block:: csharp


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
