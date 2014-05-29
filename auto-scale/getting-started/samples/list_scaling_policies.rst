.. code-block:: csharp

.. code-block:: java

  PolicyApi policyApi = autoscaleApi.getPolicyApiForZoneAndGroup("{region}", "{scalingGroupId}");
  Policy policy = policyApi.list();

.. code-block:: javascript

.. code-block:: php

    $policies = $group->getPolicies();

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    policies = au.list_policies("{scalingGroupId}")

.. code-block:: ruby

  my_group.policies

.. code-block:: sh

  $ curl -X GET -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    $ENDPOINT/groups/{groupId}/policies | python -m json.tool