.. code-block:: csharp

.. code-block:: curl

   # To restart a database instance:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" \
      -H "Content-Type: application/json" -X POST \
      -d '{"restart": {}}' \
      $publicUrl/instances/{instanceId}/action | python -m json.tool
   # NOTE: {instanceId} is a placeholder:
   # Replace it with an actual value and do not enclose it with {}.

.. code-block:: java

    // Currently not supported.

.. code-block:: javascript


.. code-block:: php

    $instance->restart();

.. code-block:: python

    inst.restart()

.. code-block:: ruby

    instance.restart
    instance.wait_for { ready? }
