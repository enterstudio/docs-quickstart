.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # {project_id} is the account ID of the member.
  member = imgs.get_image_member("{image_id}", "{project_id}")

.. code-block:: ruby

  # N/A

.. code-block:: shell

  curl -s $ENDPOINT/images/{imageId}/members/{memberId} \
    -H "X-Auth-Token: $TOKEN" | python -m json.tool

  # NOTE: {imageId} and {memberId} are placeholders:
  # Replace them with actual values and do not enclose the values with {}.
