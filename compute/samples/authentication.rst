.. code-block:: csharp

.. code-block:: java

    // Authentication in jclouds is lazy.
    // It only happens on the first call to the cloud.
    NovaApi novaApi = ContextBuilder.newBuilder("rackspace-cloudservers-us")
            .credentials("{username}", "{apiKey}")
            .buildApi(NovaApi.class);

.. code-block:: javascript

    pkgcloud = require('pkgcloud');

    // each client is bound to a specific service and provider
    var client = pkgcloud.compute.createClient({
      provider: 'rackspace',
      username: '{username}',
      apiKey: '{apiKey}',
      region: '{region}'
    });

.. code-block:: php

    require 'vendor/autoload.php';

    use OpenCloud\Rackspace;

    $client = new Rackspace(Rackspace::US_IDENTITY_ENDPOINT, array(
        'username' => '{username}',
        'apiKey'   => '{apiKey}'
    ));

.. code-block:: python

.. code-block:: ruby

    require 'fog'

    @client = Fog::Compute.new(
      :provider => 'rackspace',
      :rackspace_username => '{username}',
      :rackspace_api_key => '{apiKey}',
      :rackspace_region => '{region}'
    )

.. code-block:: shell
  
  $ curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
     -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"MyRackspaceAcct", "apiKey":"0000000000000000000"}}}' \
     -H "Content-Type: application/json" | python -m json.tool