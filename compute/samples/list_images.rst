.. code-block:: csharp

.. code-block:: java

    ImageApi imageApi = novaApi.getImageApiForZone("{region}");
    ImmutableList<? extends Image> images = imageApi.listInDetail().concat().toList();

.. code-block:: javascript

    client.getImages(function(err, images) {
      if (err) {
        // TODO handle as appropriate
        return;
      }

      // TODO figure out which image to use
      // just grab the first image id
      var imageId = images[0].id;
    });

.. code-block:: php

    // To retrieve all images:
    $images = $service->imageList();

    // Choose the first image in the collection
    foreach ($images as $image) {
        $imageId = $image->id;
        break;
    }

.. code-block:: python

    import pyrax

    img = pyrax.images
    # Get a list of the images available to your account
    image_list = img.list()
    # Shows the number of images in the list
    print("There are %s images:" % len(image_list))
    # Shows the visibility, names, and IDs of your images
    for img in image_list:
        print("  (%s) %s (ID=%s)" % (img.visibility, img.name, img.id))

.. code-block:: ruby

    @client.images.all

.. code-block:: shell

    $curl -X GET $ENDPOINT/images \
      -H "X-Auth-TOKEN: $TOKEN" | python -m json.tool