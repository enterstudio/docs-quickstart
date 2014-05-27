.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

    /** @param $member OpenCloud\Image\Resource\Member */
    $member = $image->getMember('{tenantId}');

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # {projectId} is the account ID of the member.
  member = imgs.get_image_member("{imageId}", "{projectId}")

.. code-block:: ruby

  // Fog doesn't support this API presently

.. code-block:: sh

  curl -s $ENDPOINT/images/{imageId}/members/{memberId} \
    -H "X-Auth-Token: $TOKEN" | python -m json.tool

  # NOTE: {imageId} and {memberId} are placeholders:
  # Replace them with actual values and do not enclose the values with {}.
