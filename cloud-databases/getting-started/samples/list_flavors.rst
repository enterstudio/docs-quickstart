.. code-block:: csharp

  ReadOnlyCollection<DatabaseFlavor> databaseFlavorCollection = await new CloudDatabasesProvider(cloudIdentity, "{region}", null).ListFlavorsAsync(CancellationToken.None);

.. code-block:: java

  // List your flavors and get the first.
  FlavorApi flavorApi = troveApi.getFlavorApiForZone("{region}");
  Flavor flavor = Iterables.getFirst(flavorApi.list(), null);

.. code-block:: javascript

.. code-block:: php

  $flavors = $service->flavorList();

.. code-block:: python

  flavors = cdb.list_flavors()

.. code-block:: ruby

  flavors = @client.flavors.all

.. code-block:: sh

  curl -s $ENDPOINT/flavors \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool

  # Choose the flavor you prefer and make a note of its "href" element.
  export FLAVOR_REF="{flavorRef}"

  # Remember the same "href" of another flavor for resizing, later.
  export NEW_FLAVOR_REF="{newFlavorRef}"
