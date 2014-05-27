.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $group = $service->group('{groupId}');

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    scaling_group = au.get("{scalingGroupId}")

.. code-block:: ruby

  my_group = service.groups.get '{groupId}'

.. code-block:: sh

  $ curl -X GET -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    $ENDPOINT/groups/{groupId} | python -m json.tool