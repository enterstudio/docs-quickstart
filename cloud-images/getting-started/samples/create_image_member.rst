.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

  $image->createMember('{tenantId}');

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # Call the `add_image_member()` method, passing in the ID of the image
  # and the project ID of the member to add.
  member = imgs.add_image_member("{imageId}", "{projectId}")

.. code-block:: ruby

  # Fog doesn't support this API presently

.. code-block:: sh

  # Use the prospective image consumer's Rackspace account number for {memberId}.

  curl -s -X POST $ENDPOINT/images/{imageId}/members \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json" \
    -d '{ "member": "{memberId}" }' | python -m json.tool
