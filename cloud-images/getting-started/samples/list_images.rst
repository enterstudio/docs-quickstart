.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  # To retrieve all images:
  $images = $service->imageList();

  # Choose the first image in the collection
  foreach ($images as $image) {
      $imageId = $image->id;
      break;
  }

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  all_images = imgs.list()

.. code-block:: ruby

  # N/A

.. code-block:: sh

  curl -s $ENDPOINT/images -H "X-Auth-Token: $token" | python -m json.tool
