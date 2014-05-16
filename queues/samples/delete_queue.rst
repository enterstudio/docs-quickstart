.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  $queue->delete();

.. code-block:: python

  pyrax.queues.delete("sample_queue")

.. code-block:: ruby

  queue.destroy

.. code-block:: shell

  $ curl -X DELETE $ENDPOINT/queues/{queue_name} \ 
    -H "Content-type: application/json" \ 
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "X-Project-Id: {projectId}"