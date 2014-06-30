.. code-block:: csharp

  CloudQueuesProvider cloudQueuesProvider = new CloudQueuesProvider(cloudIdentity, "{region}", Guid.NewGuid(), false, null);
  QueueName queueName = new QueueName("{queue_name}");
  await cloudQueuesProvider.DeleteQueueAsync(queueName, CancellationToken.None);

.. code-block:: java

  QueueApi queueApi = marconiApi.getQueueApiForZoneAndClient("{region}", "{clientId}");
  queueApi.delete("sample_queue");

.. code-block:: javascript

.. code-block:: php

  $queue->delete();

.. code-block:: python

  pyrax.queues.delete("sample_queue")

.. code-block:: ruby

  queue.destroy

.. code-block:: sh

  curl -X DELETE $ENDPOINT/queues/{queueName} \
    -H "Content-type: application/json" \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "X-Project-Id: {projectId}"
