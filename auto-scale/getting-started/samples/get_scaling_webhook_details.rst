.. code-block:: csharp

  Webhook webhook = await cloudAutoScaleProvider.GetWebhookAsync({group_id}, {policy_id}, {webhook_id}, CancellationToken.None);

.. code-block:: java

  WebhookApi webhookApi = autoscaleApi.getWebhookApiForZoneAndGroupAndPolicy("{region}", "{groupId}", "{policyId}");
  Webhook webhook = webhookApi.get("{webhookId}");

.. code-block:: javascript

.. code-block:: php

  $webhook = $policy->getWebhook('{webhookId}');

.. code-block:: python

  # After authenticating
  au = pyrax.autoscale
  webhook = au.get_webhook("{scalingGroupId}", "{policyId}", "{webhookId}")

.. code-block:: ruby

  my_webhook = my_policy.webhooks.get '{webhookId}'

.. code-block:: sh

  curl -X GET $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
