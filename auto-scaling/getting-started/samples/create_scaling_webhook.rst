.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    # Note: the `metadata` parameter is optional.
    webhook = au.add_webhook("{scalingGroupId}", "{policyId}",
            name="My Webhook", metadata={"someKey": "someValue"})

.. code-block:: ruby

  my_webhook = my_policy.webhooks.create :name => 'my-webhook'
