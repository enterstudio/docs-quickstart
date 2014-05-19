.. code-block:: csharp

.. code-block:: java

  ServerApi serverApi = novaApi.getServerApiForZone("{region}");
  ServerCreated serverCreated = serverApi.create("My new server", "{imageId}", "{flavorId}");

.. code-block:: javascript

  client.createServer({
    name: 'My new server',
    image: imageId,
    flavor: flavorId
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
      ));
  } catch (BadResponseException $e) {
      // No! Something failed. Let's find out:
      printf("Request: %s\n\nResponse: %s", (string) $e->getRequest(), (string) $e->getResponse());
  }

.. code-block:: python

  cs = pyrax.cloudservers
  server = cs.servers.create('My new server', image.id, flavor.id)

.. code-block:: ruby

  server = @client.servers.create(
    :name => 'My new server',
    :image_id => image.id,
    :flavor_id => flavor.id
  )

.. code-block:: shell

  # Reminder: all {variableNames} are placeholders only. Must be replaced by actual and valid values
  curl -X POST $ENDPOINT -d \
    '{
      "server" : {
          "name" : "My new server",
          "imageRef" : $IMAGE_ID,
          "flavorRef" : $FLAVOR_ID
        }
      }' -H "X-Auth-Token: $TOKEN" | python -m json.tool

  export SERVER_ID="{serverId}"
