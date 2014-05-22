.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    # The `scaling_group_id`, `policy_id`, and `webhook_id` parameters are
    # required. You may include one or more of the remaining parameters.
    au.update_webhook("{scaling_group_id}", "{policy_id}", "{webhook_id}",
            "{name}", {metadata})

.. code-block:: ruby

  my_webhook.name = 'webhook1'
  my_webhook.metadata = {
      :owner => 'webteam'
  }
  my_webhook.save
