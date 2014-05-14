.. code-block:: csharp

.. code-block:: java

    ImageApi imageApi = novaApi.getImageApiForZone("{region}");
    Image image = imageApi.get("{imageId}");

.. code-block:: javascript

    client.getImage(imageId, function(err, image) {
      if (err) {
        // TODO handle as appropriate
        return;
      }

      // TODO use your image here
    });

.. code-block:: php

    $imageId = '{imageId}';
    $image = $service->image($imageId);

.. code-block:: python

    import pyrax

    img = pyrax.images
    # Get a list of the images available to your account
    image_list = img.list()
    image_name = [img in cs.images.list()
        if "Fedora 20" in img.name][0]

.. code-block:: ruby

    image = @client.images.get('{imageId}')
