.. code-block:: csharp

  TimeSpan cooldown = TimeSpan.FromSeconds(120);
  int desiredCapacity = 1;
  PolicyConfiguration policyConfiguration = PolicyConfiguration.Capacity("New Name", desiredCapacity, cooldown);
  await cloudAutoScaleProvider.SetPolicyAsync(scalingGroup.Id, policy.Id, policyConfiguration, CancellationToken.None);

.. code-block:: java

  PolicyApi policyApi = autoscaleApi.getPolicyApiForZoneAndGroup("{region}", "{scalingGroupId}");
  CreateScalingPolicy scalingPolicy = CreateScalingPolicy.builder()
            .cooldown(120)
            .type(ScalingPolicyType.WEBHOOK)
            .name("New Name")
            .targetType(ScalingPolicyTargetType.INCREMENTAL)
            .target("1")
            .build();

  policyApi.update("{policyId}", scalingPolicy);

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  $policy->update(array(
      'name'     => 'New name',
      'cooldown' => 120
  ));

.. code-block:: python

  au.update_policy("{groupId}", "{policyId}", name="New Name",
          policy_type="webhook", cooldown=120, change=10, is_percent=True,
          desired_capacity=1)

.. code-block:: ruby

  my_policy.name = 'New Name'
  my_policy.cooldown = 120
  my_policy.save

.. code-block:: sh

  curl -X PUT $ENDPOINT/groups/{scalingGroupId}/policies/{policyId} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d '{
      "change": 10,
      "cooldown": 120,
      "name": "New Name",
      "type": "webhook"
    }' | python -m json.tool
