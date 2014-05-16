.. code-block:: csharp

.. code-block:: java

    CreateServerOptions options = CreateServerOptions.Builder.keyPairName("my-keypair");
    ServerApi serverApi = novaApi.getServerApiForZone("{region}");
    ServerCreated serverCreated = serverApi.create("My new server", "{imageId}", "{flavorId}", options);

.. code-block:: javascript

    client.createServer({
      name: 'My new server',
      image: imageId,
      flavor: flavorId,
      keyname: 'my_keypair'
    }, function(err, server) {
      if (err) {
        // TODO handle as appropriate
        return;
      }

      // TODO use your server here
    });

.. code-block:: php

    use Guzzle\Http\Exception\BadResponseException;

    $server = $compute->server();

    try {
        $response = $server->create(array(
            'name'     => 'My new server',
            'imageId'  => $imageId,
            'flavorId' => $flavorId
            'keypair'  => 'my_keypair'
        ));
    } catch (BadResponseException $e) {
        // No! Something failed. Let's find out:
        printf("Request: %s\n\nResponse: %s", (string) $e->getRequest(), (string) $e->getResponse());
    }

.. code-block:: python

.. code-block:: ruby

    server = @client.servers.create(
      :name => 'My new server',
      :image_id => image.id,
      :flavor_id => flavor.id,
      :key_name => 'my_keypair'
    )

.. code-block:: shell

    $ curl -X POST $ENDPOINT -d \
      '{
      "server" : {
          "name" : "{serverName}",
          "imageRef" : "{imageRefId}",
          "flavorRef" : "{flavorRefNumber}",
          "key_name" : "{nameOfKeyPair}"        
        }
      }' -H "X-Auth-TOKEN: $TOKEN" | python -m json.tool
