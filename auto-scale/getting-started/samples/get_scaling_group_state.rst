.. code-block:: csharp

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  GroupState groupState = groupApi.getState("{scalingGroupId}");

.. code-block:: javascript

.. code-block:: php

  $state = $group->getState();

.. code-block:: python

  # After authenticating
  au = pyrax.autoscale
  state = au.get_state("{scalingGroupId}")

.. code-block:: ruby

  my_group.state

.. code-block:: sh

  curl -X GET $ENDPOINT/groups/{groupId}/state \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
