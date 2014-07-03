.. code-block:: csharp

  // Not currently supported by this SDK

.. code-block:: java

  // Not currently supported by this SDK

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

    $image   = $service->getImage('{imageId}');
    $imageId = $image['id'];

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  img = imgs.get("{imageId}")

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

  curl -s $ENDPOINT/images/{imageId} \
    -H "X-Auth-Token: $TOKEN" | python -m json.tool
