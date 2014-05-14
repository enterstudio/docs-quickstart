.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

  queue = pyrax.queues.get("sample_queue")

  # The 'body' parameter can be a simple value, or a chunk of XML, or pretty
  #   much anything you need.
  # The 'ttl' parameter sets the life of the message (in seconds).

  queue.post_message("Message body", ttl=900)

.. code-block:: ruby

  # The 'body' parameter can be a String, a Hash, or an Array.
  # The 'ttl' parameter sets the life of the message (in seconds).

  queue.enqueue("Message body", 900)
