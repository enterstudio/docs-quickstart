.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    au.add_policy("{scaling_group_id}", "{policy_name}", {cooldown},
            {change}, {is_percent}) 
    # Parameter explanations:
    #   scaling_group_id: ID of the scaling group to which you are
    #       adding the policy
    #   policy_name: Name for the new policy
    #   cooldown: period to wait between applications of scaling actions
    #   change: Scaling increment
    #   is_percent: Determines whether the value of the `change` parameter
    #       is a percentage or an absolute number

.. code-block:: ruby

  my_policy = my_group.policies.create :name => 'Scale by one server', 
    :cooldown => 360, 
    :type => 'webhook', 
    :change => 1
