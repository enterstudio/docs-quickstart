.. code-block:: csharp

.. code-block:: java

    FlavorApi flavorApi = novaApi.getFlavorApiForZone("{region}");
    ImmutableList<? extends Flavor> flavors = flavorApi.listInDetail().concat().toList();

.. code-block:: javascript

    client.getFlavors(function(err, flavors) {
      if (err) {
        // TODO handle as appropriate
        return;
      }

      // TODO figure out which flavors to use
      // just grab the first flavor id
      var flavorId = flavors[0].id;
    });

.. code-block:: php

    // To retrieve all flavors:
    $flavors = $service->flavorList();

    // or to retrieve a subset of flavors, you can specify the
    // minimum disk storage (in GB) or minimum RAM (in MB)
    $flavors = $service->flavorList(false, array(
        'minDisk' => 100,
        'minRam'  => 16 * 1024
    ));

    // Now choose the first flavor in the collection
    foreach ($flavors as $flavor) {
        $flavorId = $flavor->id;
        break;
    }

.. code-block:: python

    import pyrax

    cs = pyrax.cloudservers
    # Get a list of the flavors available to your account
    flavor_list = cs.list_flavors()
    # Shows the number of flavors in the list
    print("There are %s flavors:" % len(flavor_list))
    # Shows flavor names, IDs, RAM, disk space, and number of vCPUs
    for flv in flavor_list:
        print("Name:", flv.name)
        print("  ID:", flv.id)
        print("  RAM:", flv.ram)
        print("  Disk:", flv.disk)
        print("  VCPUs:", flv.vcpus)
        print()

.. code-block:: ruby

    @client.flavors.all

.. code-block:: shell

    $curl -X GET $endpoint/flavors \
    -H "X-Auth-Token: $token" | python -m json.tool
