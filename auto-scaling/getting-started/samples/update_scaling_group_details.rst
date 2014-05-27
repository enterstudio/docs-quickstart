.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    # The scaling group ID is required. You may include one or more of
    # the other parameters.
    au.update("{scalingGroupId}", name="My Group", cooldown=120,
            min_entities=1, max_entities=25, metadata={"someKey": "someValue"})

.. code-block:: ruby

  group_config = my_group.group_config
  
  group_config.cooldown = 120
  group_config.max_entities = 16
  group_config.save

.. code-block:: sh

  $ curl -X PUT -d \
    '{
     "name":"{groupName}",
     "cooldown":60,
     "minEntities":{newMinServers},
     "maxEntities":{newMaxServers}
    }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    $ENDPOINT/groups/{groupId}/config