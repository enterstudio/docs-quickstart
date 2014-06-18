.. code-block:: csharp

.. code-block:: curl

   # To resize a database instance:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" -X POST \
      -d '{"resize": {"flavorRef": "https://ord.databases.api.rackspacecloud.com/v1.0/{account}/flavors/{flavorId}"}}' \
      $publicUrl/instances/{instanceId}/action | python -m json.tool
   # NOTE: {account}, {flavorId}, and {instanceId} are placeholders:
   # Replace them with an actual values and do not enclose them with {}.

.. code-block:: java

    // Currently not supported.

.. code-block:: javascript


.. code-block:: php

    $instance->resize($flavor);

.. code-block:: python

    inst.resize(new_flavor)

.. code-block:: ruby

    instance.resize(new_flavor.id)
    instance.wait_for { ready? }
