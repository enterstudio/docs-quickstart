.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    # The scaling group ID is required. You may include one or more of
    # the other parameters.
    au.update("{scaling_group_id}", "{name}", {cooldown},
            {min_entities}, {max_entities}, {metadata})

.. code-block:: ruby

  group_config = my_group.group_config
  
  group_config.cooldown = 120
  group_config.max_entities = 16
  group_config.save
