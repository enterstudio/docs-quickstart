.. code-block:: csharp

.. code-block:: curl

   # To get flavor details:
   $ curl -s -H "X-Auth-Token: $token" -H "Accept: application/json" \
       $publicUrl/flavors/{flavorId} | python -m json.tool
   # NOTE: {flavorId} is a placeholder:
   # Replace it with an actual value and do not enclose it with {}.

.. code-block:: java

    Flavor flavor = flavorApi.get({flavorId});

.. code-block:: javascript


.. code-block:: php

    $flavorId = '{flavorId}';
    $flavor = $service->flavor($flavorId);

.. code-block:: python

    flavor = cdb.get_flavor(flavor_id)

.. code-block:: ruby

    flavor = @client.flavors.get('{flavorId}')
