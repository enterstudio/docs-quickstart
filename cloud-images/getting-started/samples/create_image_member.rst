.. code-block:: csharp

  // Not currently supported by this SDK

.. code-block:: java

  // Not currently supported by this SDK

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  $image->createMember('{tenantId}');

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # Call the `add_image_member()` method, passing in the ID of the image
  # and the project ID of the member to add.
  member = imgs.add_image_member("{imageId}", "{projectId}")

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

  # Use the prospective image consumer's Rackspace account number for {memberId}.

  curl -s -X POST $ENDPOINT/images/{imageId}/members \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json" \
    -d '{ "member": "{memberId}" }' | python -m json.tool
