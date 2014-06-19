.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

  $image->createMember('{tenantId}');

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # {tenantId} is the account ID to share the image with.
  imgs.add_image_member("{imageId}", "{tenantId}")

.. code-block:: ruby

  # Fog doesn't support this API presently

.. code-block:: sh
