.. code-block:: csharp

.. code-block:: java

    FlavorApi flavorApi = novaApi.getFlavorApiForZone("{region}");
    Flavor flavor = flavorApi.get("{flavorId}");

.. code-block:: javascript

    client.getFlavor(flavorId, function(err, flavor) {
      if (err) {
        // TODO handle as appropriate
        return;
      }

      // TODO use your flavor here
    });

.. code-block:: php

    $flavorId = '{flavorId}';
    $flavor = $service->flavor($flavorId);

.. code-block:: python

    import pyrax

    cs = pyrax.cloudservers
    # Get a list of flavors available in your account
    flavor = cs.list_flavors()
    flavor_1GB_perf = [flavor for flavor in cs.flavors.list()
        if flavor.name == "1 GB Performance"][0]

.. code-block:: ruby

    flavor = @client.flavor.get('{flavorId}')

.. code-block:: shell

    $curl -X GET $ENDPOINT/flavors/{flavorId} \
        -H "X-Auth-TOKEN: $TOKEN" | python -m json.tool