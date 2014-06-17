.. code-block:: csharp

.. code-block:: java

  PolicyApi policyApi = autoscaleApi.getPolicyApiForZoneAndGroup("{region}", "{scalingGroupId}");
  CreateScalingPolicy scalingPolicy = CreateScalingPolicy.builder()
            .cooldown(3)
            .type(ScalingPolicyType.WEBHOOK)
            .name("New name")
            .targetType(ScalingPolicyTargetType.INCREMENTAL)
            .target("1")
            .build();

  policyApi.update("{policyId}", scalingPolicy);

.. code-block:: javascript

.. code-block:: php

    $policy->update(array(
        'name'     => 'New name',
        'cooldown' => 120
    ));

.. code-block:: python

    au = pyrax.autoscale
    au.update_policy("{scalingGroupId}", "{policyId}", name="My Policy",
            policy_type="webhook", cooldown=120, change=10, is_percent=True,
            desired_capacity=7)

.. code-block:: ruby

  my_policy.cooldown = 60
  my_policy.change = 3
  my_policy.save

.. code-block:: sh

  $ curl -X PUT -d \
    '{
         "change":1,
         "cooldown":{newCooldown},
         "name":"scale up by one server",
         "type":"webhook"
      }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    $ENDPOINT/groups/{scalingGroupId}/policies/{policyId}
