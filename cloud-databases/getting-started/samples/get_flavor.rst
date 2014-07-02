.. code-block:: csharp

  FlavorId flavorId = new FlavorId("{flavor_id}");
  DatabaseFlavor databaseFlavor = await cloudDatabasesProvider.GetFlavorAsync(flavorId, CancellationToken.None);

.. code-block:: java

  Flavor flavor = flavorApi.get("{flavorId}");

.. code-block:: javascript

  client.getFlavor({flavorId}, function(err, flavor) {
    if (err) {
      // TODO handle as appropriate
    }

    // TODO use your flavor here
  });

.. code-block:: php

  $flavor = $service->flavor('{flavorId}');

.. code-block:: python

  flavor = cdb.get_flavor('{flavorId}')

.. code-block:: ruby

  flavor = @client.flavors.get('{flavorId}')

.. code-block:: sh

  curl -s $ENDPOINT/flavors/{flavorId} \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
