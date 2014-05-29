.. code-block:: csharp

.. code-block:: java

  WebhookApi webhookApi = autoscaleApi.getWebhookApiForZoneAndGroupAndPolicy("{region}", "{groupId}", "{policyId}");
  FluentIterable<Webhook> webhooks = webhookApi.list();

.. code-block:: javascript

.. code-block:: php

    $webhooks = $policy->getWebhookList();

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    webhooks = au.list_webhooks("{scalingGroupId}", "{policyId}")

.. code-block:: ruby

  my_policy.webhooks

.. code-block:: sh
  
  $ curl -X GET -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks \
    | python -m json.tool