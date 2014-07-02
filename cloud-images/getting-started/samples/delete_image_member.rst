.. code-block:: csharp

  // Not currently supported by this SDK

.. code-block:: java

  // Not currently supported by this SDK

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

    $image->deleteMember('{tenantId}');

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # Call the `delete_image_member()` method, passing in the ID of the image
  # and the project ID of the member to be removed.
  imgs.delete_image_member("{imageId}", "{projectId}")

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

  curl -i -X DELETE $ENDPOINT/images/{imageId}/members/{memberId} \
      -H "X-Auth-Token: $TOKEN"
