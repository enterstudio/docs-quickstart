.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $state = $group->getState();

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    state = au.get_state("{scalingGroupId}")

.. code-block:: ruby

  my_group.state

.. code-sample:: sh

  $ curl -X GET -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    $ENDPOINT/groups/{groupId}/state | python -m json.tool