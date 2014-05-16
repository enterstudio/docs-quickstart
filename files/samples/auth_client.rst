.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

   pkgcloud = require('pkgcloud');

    // each client is bound to a specific service and provider
    var client = pkgcloud.storage.createClient({
      provider: 'rackspace',
      username: '{username}',
      apiKey: '{apiKey}',
      region: '{region}'
    });

.. code-block:: php

    require 'vendor/autoload.php';

    use OpenCloud\Rackspace;

    // Instantiate a Rackspace client.
    $client = new Rackspace(Rackspace::US_IDENTITY_ENDPOINT, array(
        'username' => '{username}',
        'apiKey'   => '{apiKey}'
    ));

.. code-block:: python

  import pyrax
  pyrax.set_setting("identity_type", "rackspace")
  pyrax.set_default_region({region})
  pyrax.set_credentials({username}, {apiKey})

.. code-block:: ruby

  require 'fog'

  # ":rackspace_region" determines which geographic region your data will be
  # stored in. Valid choices include :dfw (Dallas), :ord (Chicago), :iad
  # (Virginia), :syd (Sydney), and :hkg (Hong Kong).

  @client = Fog::Storage.new(
    :provider => 'rackspace',
    :rackspace_username => '{username}',
    :rackspace_api_key => '{apiKey}',
    :rackspace_region => '{region}'
  )

  # If you're a UK customer, specify a :rackspace_auth_url of "Fog::Rackspace::UK_AUTH_ENDPOINT" as well, and use the
  # :lon (London) region.
  
.. code-block:: curl
    
    # {username}, {apiKey} below are placeholders, do not enclose '{}' when you replace them with actual credentials.

    $ curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
       -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"{username}", "apiKey":"{apiKey}"}}}' \
       -H "Content-Type: application/json" | python -m json.tool

    # From the resulting json, set three environment variables: tenant, TOKEN and endpoint

    $ export TENANT="{tenantId}"
    $ export TOKEN="{TokenId}"
    $ export ENDPOINT={publicUrl} #for cloud files service