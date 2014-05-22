.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # Call the `delete_image_member()` method, passing in the ID of the image
  # and the project_id of the member to be removed.
  imgs.delete_image_member("{image_id}", "{project_id}")

.. code-block:: ruby

  # N/A

.. code-block:: shell

  curl -i $ENDPOINT/images/{imageId}/members/{memberId} -X DELETE \
      -H "X-Auth-Token: $TOKEN"

  # NOTE: {imageId} and {memberId} are placeholders:
  # Replace them with actual values and do not enclose the values with {}.
