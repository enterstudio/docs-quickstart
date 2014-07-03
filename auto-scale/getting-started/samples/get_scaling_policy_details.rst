.. code-block:: csharp

  Policy policy = await cloudAutoScaleProvider.GetPolicyAsync(scalingGroup.Id, {policyId}, CancellationToken.None);

.. code-block:: java

  PolicyApi policyApi = autoscaleApi.getPolicyApiForZoneAndGroup("{region}", "{groupId}");
  Policy policy = policyApi.get("{policyId}");

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

    $policy = $group->getScalingPolicy('{policyId}');

.. code-block:: python

  policy = au.get_policy("{groupId}", "{policyId}")

.. code-block:: ruby

  my_policy = my_group.policies.get('{policyId}')

.. code-block:: sh

  curl -X GET $ENDPOINT/groups/{groupId}/policies/{policyId} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
