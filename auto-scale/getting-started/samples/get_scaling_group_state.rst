.. code-block:: csharp

  GroupState groupState = await cloudAutoScaleProvider.GetGroupStateAsync(scalingGroup.Id, CancellationToken.None);

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  GroupState groupState = groupApi.getState("{groupId}");

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  $state = $group->getState();

.. code-block:: python

  state = au.get_state("{groupId}")

.. code-block:: ruby

  my_group.state

.. code-block:: sh

  curl -X GET $ENDPOINT/groups/{groupId}/state \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
