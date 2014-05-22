.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    # The `scaling_group_id` and `policy_id` parameters are required. You may
    # include one or more of the remaining paramters.
    au.update_policy("{scaling_group_id}", "{policy_id}", "{name}",
            "{policy_type}", {cooldown}, {change}, {is_percent},
            {desired_capacity})

.. code-block:: ruby

  my_policy.cooldown = 60
  my_policy.change = 3
  my_policy.save
