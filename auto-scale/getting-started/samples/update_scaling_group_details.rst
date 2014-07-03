.. code-block:: csharp

  TimeSpan cooldown = TimeSpan.FromSeconds(60);
  await cloudAutoScaleProvider.SetGroupConfigurationAsync(scalingGroup.Id, new GroupConfiguration("New Name", cooldown, 0, 0, new JObject()), CancellationToken.None);

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  GroupConfiguration groupConfiguration = GroupConfiguration.builder()
            .minEntities(2)
            .maxEntities(6)
            .cooldown(60)
            .name("New Name")
            .metadata(ImmutableMap.of("someKey", "someValue"))
            .build();
  
  groupApi.updateGroupConfiguration("{groupId}", groupConfiguration);

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  // Not currently supported by this SDK

.. code-block:: python

  au.update("{groupId}", name="My Group", cooldown=120,
          min_entities=2, max_entities=6, metadata={"someKey": "someValue"})

.. code-block:: ruby

  group_config = my_group.group_config

  group_config.name = 'New Name'
  group_config.max_entities = 6
  group_config.save

.. code-block:: sh

  $ curl -X PUT $ENDPOINT/groups/{scalingGroupId}/config \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d '{
       "name": "My Group",
       "cooldown": 60,
       "minEntities": 2,
       "maxEntities": 6
     }' | python -m json.tool
