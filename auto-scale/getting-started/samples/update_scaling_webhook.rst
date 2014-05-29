.. code-block:: csharp

.. code-block:: java
WebhookApi webhookApi = autoscaleApi.getWebhookApiForZoneAndGroupAndPolicy("{region}", "{groupId}", "{policyId}");
boolean result = webhookApi.update("{webhookId}","New name", ImmutableMap.<String, Object>of());

.. code-block:: javascript

.. code-block:: php

    $webhook->update(array(
        'metadata' => array(
            'someKey' => 'someValue'
        )
    ));

.. code-block:: python

    au = pyrax.autoscale
    au.update_webhook("{scalingGroupId}", "{policyId}", "{webhookId}",
            name="My Webhook", metadata={"someKey": "someValue"})

.. code-block:: ruby

  my_webhook.name = 'webhook1'
  my_webhook.metadata = {
      :owner => 'webteam'
  }
  my_webhook.save

.. code-block:: sh

  $ curl -X PUT -d \
    '{
    "name": "alice",
    "metadata": {
        "notes": "{newNote}"
          }
      }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks/{webhookId}
