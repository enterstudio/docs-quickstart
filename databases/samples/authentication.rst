.. code-block:: csharp

.. code-block:: curl

   # Export your publicURL to the publicUrl variable:
   $ export publicUrl="https://identity.api.rackspacecloud.com/v2.0/"
   # To authenticate, use your Rackspace Cloud Account user name and API key:
   $ curl -s $publicUrl/tokens -X 'POST' \
       -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"{username}", "apiKey":"{apiKey}"}}}' \
       -H "Content-Type: application/json" | python -m json.tool
   # NOTE: {username} and {apiKey} are placeholders:
   # Replace them with actual values and do not enclose the values with {}.
   #
   # Export the publicURL for cloudDatabases to the publicUrl variable,
   # and your authentication token to the token variable.
   $ export publicUrl="https://syd.databases.api.rackspacecloud.com/v1.0/{account}"
   $ export token="{token}"
   # NOTE: {account} and {token} are placeholders:
   # Replace them with actual values and do not enclose the values with {}.

.. code-block:: java

  // The TroveApi will provide access to all database features, such as Instances or Users.
  TroveApi troveApi = ContextBuilder.newBuilder("rackspace-clouddatabases-us")
          .credentials("{username}", "{apiKey}"")
          .buildApi(TroveApi.class);

.. code-block:: javascript

  pkgcloud = require('pkgcloud');
  var rackspace = pkgcloud.dns.createClient({
    provider: 'rackspace',
    username: '{username}',
    apiKey: '{apiKey}'
  });

.. code-block:: php

    require 'vendor/autoload.php';

    use OpenCloud\Rackspace;

    $client = new Rackspace(Rackspace::US_IDENTITY_ENDPOINT, array(
        'username' => '{username}',
        'apiKey'   => '{apiKey}'
    ));

.. code-block:: python

  import pyrax
  pyrax.set_credentials({username}, {api_key}, region={region})
  cdb = pyrax.cloud_databases

.. code-block:: ruby

  require 'fog'

  @client = Fog::Rackspace::Databases.new(
    :rackspace_username => '{username}',
    :rackspace_api_key => '{apiKey}',
    :rackspace_region => '{region}'
  )
