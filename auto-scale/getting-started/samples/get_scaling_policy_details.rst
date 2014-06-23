.. code-block:: csharp

.. code-block:: java

  PolicyApi policyApi = autoscaleApi.getPolicyApiForZoneAndGroup("{region}", "{scalingGroupId}");
  Policy policy = policyApi.get("{policyId}");

.. code-block:: javascript

.. code-block:: php

    $policy = $group->getScalingPolicy('{policyId}');

.. code-block:: python

  # After authenticating
  au = pyrax.autoscale
  policy = au.get_policy("{scalingGroupId}", "{policyId}")

.. code-block:: ruby

  my_policy = my_group.policies.get '{policyId}'

.. code-block:: sh

  curl -X GET $ENDPOINT/groups/{groupId}/policies/{policyId} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
