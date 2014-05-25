.. code-block:: csharp

.. code-block:: java

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

  $ curl -X GET -H "X-Auth-Token: $TOKEN" \
  $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks \
  | python -m json.tool