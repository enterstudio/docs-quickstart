.. code-block:: csharp

.. code-block:: curl

   # To show the root-enabled status for a database instance:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" -X GET \
      $publicUrl/instances/{instanceId}/root | python -m json.tool
   # The command returns True if the root user is enabled for the specified
   # database instance.
   # NOTE: {instanceId} is a placeholder:
   # Replace it with an actual values and do not enclose it with {}.
   
.. code-block:: java

    InstanceApi instanceApi = troveApi.getInstanceApiForZone("{region}");

    boolean rootedStatus = instanceApi.isRooted("{instanceId}");

.. code-block:: javascript


.. code-block:: php

    if (true === $instance->isRootEnabled()) {
        // yes it is
    }

.. code-block:: python

    root_enabled = cdb.root_user_status()

.. code-block:: ruby

    instance.root_user_enabled?
