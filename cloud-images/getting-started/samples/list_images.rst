.. code-block:: csharp

  // Not currently supported by this SDK

.. code-block:: java

  // Not currently supported by this SDK

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

    $service = $client->imageService('cloudImages', '{regionId}');
    $images  = $service->listImages();

    foreach ($images as $image) {
       /** @param $image OpenCloud\Image\Resource\Image */
    }

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  all_images = imgs.list()

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

  curl -s $ENDPOINT/images -H "X-Auth-Token: $TOKEN" | python -m json.tool
