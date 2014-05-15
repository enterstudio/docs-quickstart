.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

   // Delete claimed messages.               
   foreach ($claimedMessages as $claimedMessage) {
       $claimId = $claimedMessage->getClaimIdFromHref();
       $claimedMessage->delete($claimId);
   }

.. code-block:: python

  queue = pyrax.queues.get("sample_queue")

  # If the message has not been claimed:
  queue.delete_message(message_id)

  # If the message has been claimed, you need to include the claim_id:
  queue.delete_message(message_id, claim_id="01234356789abcdef")

.. code-block:: ruby

  message.destroy
