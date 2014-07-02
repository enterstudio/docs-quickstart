.. code-block:: csharp

  await cloudAutoScaleProvider.DeleteGroupAsync({group_id}, true, CancellationToken.None);

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  boolean result = groupApi.delete("{groupId}");

.. code-block:: javascript

.. code-block:: php

  $group->delete();

.. code-block:: python

  # After authenticating
  au = pyrax.autoscale
  au.delete("{scalingGroupId}")

.. code-block:: ruby

  my_group.destroy

.. code-block:: sh

  curl -X DELETE $ENDPOINT/groups/{groupId} \
    -H "X-Auth-Token: $TOKEN" \
