.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  $queues = $queuesService->listQueues();

.. code-block:: python

  pyrax.queues.list()

.. code-block:: ruby

  @client.queues.all

.. code-block:: shell

  $ curl -X GET {$endpoint}/queues \
  -H "Content-type: application/json" \ 
  -H "X-Auth-Token: {$token}" \
  -H "Accept: application/json" \
  -H "X-Project-Id: {projectId}"
