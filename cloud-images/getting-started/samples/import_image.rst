.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

  // Not currently supported

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # Create the import task. This is the most basic format for the call.
  task = imgs.import_task("My Image", "exportSwiftContainer")
  # You can optionally specify the format (default=VHD), and give the imported
  # image a new name
  task = imgs.import_task("My Image", "exportSwiftContainer",
        img_format="someOddFormat", img_name = "My New Image"))
  # Wait for the task to complete
  pyrax.utils.wait_for_build(task, verbose=True,
        desired=["success", "failure"])
  # The task's `status` attribute will be either "success" or "failure".
  # In the case of a failure, its `message` attribute will explain why.

.. code-block:: ruby

  # Fog doesn't support this API presently

.. code-block:: sh

  curl -s $ENDPOINT/tasks -X POST \
    -H "X-Auth-Token: $TOKEN" \
    -d '{
      "type": "import",
      "input": {
        "image_properties": {
          "name": "My New Image"
        },
        "import_from": "exportSwiftContainer/my-image.vhd"
      }
    }' | python -m json.tool
