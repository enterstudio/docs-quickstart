.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

    $image->deleteMember('{tenantId}');

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # Call the `delete_image_member()` method, passing in the ID of the image
  # and the project ID of the member to be removed.
  imgs.delete_image_member("{imageId}", "{projectId}")

.. code-block:: ruby

  # Fog doesn't support this API presently

.. code-block:: sh

  curl -i -X DELETE $ENDPOINT/images/{imageId}/members/{memberId} \
      -H "X-Auth-Token: $TOKEN"
