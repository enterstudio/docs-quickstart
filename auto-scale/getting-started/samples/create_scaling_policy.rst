.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $policy = $group->getPolicy();
    $policy->create(array(
        (object) array(
            'name'     => 'My policy',
            'change'   => 1,
            'type'     => 'webhook',
            'cooldown' => 360
        )
    ));

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    au.add_policy("{scalingGroupId}", "My Policy", cooldown=360, change=1,
                  is_percent=False)

.. code-block:: ruby

  my_policy = my_group.policies.create :name => 'Scale by one server',
    :cooldown => 360,
    :type => 'webhook',
    :change => 1

.. code-block:: sh

  $ curl -X POST -d \
    '[
       {
          "name":"{policyName}",
          "change":1,
          "cooldown":360,
          "type":"webhook"
       }
    ]' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    $ENDPOINT/groups/{groupId}/policies | python -m json.tool
