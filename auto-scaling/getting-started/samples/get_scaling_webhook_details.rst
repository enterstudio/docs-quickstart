.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    webhook = au.get_webhook("{scaling_group_id}", "{policy_id}",
            "{webhook_id}")

.. code-block:: ruby

  my_webhook = my_policy.webhooks.get '{webhookId}'
