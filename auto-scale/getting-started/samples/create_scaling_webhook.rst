.. code-block:: csharp

  NewWebhookConfiguration webhookConfiguration = new NewWebhookConfiguration("My Webhook");
  Webhook webhook = await cloudAutoScaleProvider.CreateWebhookAsync(scalingGroup.Id, scalingGroup.ScalingPolicies[0].Id, webhookConfiguration, CancellationToken.None);

.. code-block:: java

  WebhookApi webhookApi = autoscaleApi.getWebhookApiForZoneAndGroupAndPolicy("{region}", "{groupId}", "{policyId}");
  FluentIterable<Webhook> result = webhookApi.create("My Webhook", ImmutableMap.<String, Object>of());

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  $webook = $policy->getWebhook();
  $webhook->create(array(
      (object) array(
          'name'     => 'My Webhook',
          'metadata' => array('someKey'  => 'someValue')
      )
  ));

.. code-block:: python

  # Note: the `metadata` parameter is optional.
  webhook = au.add_webhook("{groupId}", "{policyId}",
          name="My Webhook", metadata={"someKey": "someValue"})

.. code-block:: ruby

  my_webhook = my_policy.webhooks.create(:name => 'My Webhook')

.. code-block:: sh

  curl -X POST $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d '[
      {
        "metadata": {
           "someKey": "someValue"
        },
        "name": "My Webhook"
      }
    ]' | python -m json.tool
