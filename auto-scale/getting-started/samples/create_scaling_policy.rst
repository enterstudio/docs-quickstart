.. code-block:: csharp

  PolicyConfiguration policyConfiguration = PolicyConfiguration.Capacity("My Policy", 0, TimeSpan.FromSeconds(360));
  Policy policy = await cloudAutoScaleProvider.CreatePolicyAsync(scalingGroup.Id, policyConfiguration, CancellationToken.None);

.. code-block:: java

  PolicyApi policyApi = autoscaleApi.getPolicyApiForZoneAndGroup("{region}", "{groupId}");
  CreateScalingPolicy scalingPolicy = CreateScalingPolicy.builder()
            .cooldown(360)
            .type(ScalingPolicyType.WEBHOOK)
            .name("My Policy")
            .targetType(ScalingPolicyTargetType.INCREMENTAL)
            .target("1")
            .build();
  FluentIterable<ScalingPolicy> policies = policyApi.create(ImmutableList.of(scalingPolicy));

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  $policy = $group->getScalingPolicy();
  $policy->create(array(
      array(
      (object) array(
          'name'     => 'My Policy',
          'change'   => 1,
          'type'     => 'webhook',
          'cooldown' => 360
      )

));

.. code-block:: python

  au.add_policy("{groupId}", "My Policy", cooldown=360, change=1,
                is_percent=False)

.. code-block:: ruby

  my_policy = my_group.policies.create(
    :name => 'My policy',
    :cooldown => 360,
    :type => 'webhook',
    :change => 1
  )

.. code-block:: sh

  curl -X POST $ENDPOINT/groups/{groupId}/policies \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d '[
       {
          "name": "My Policy",
          "change": 1,
          "cooldown": 360,
          "type": "webhook"
       }
    ]' | python -m json.tool
