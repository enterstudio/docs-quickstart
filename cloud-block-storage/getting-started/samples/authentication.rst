.. code-block:: csharp

  CloudIdentity cloudIdentity = new CloudIdentity()
  {
      APIKey = "{apiKey}",
      Username = "{username}"
  };
  CloudIdentityProvider cloudIdentityProvider = new CloudIdentityProvider(cloudIdentity);
  UserAccess userAccess = cloudIdentityProvider.Authenticate(cloudIdentity);
  CloudBlockStorageProvider cbsProvider = new CloudBlockStorageProvider(cloudIdentity);

.. code-block:: java

  // Authentication in jclouds is lazy and happens on the first call to the cloud.
  CinderApi cinderApi = ContextBuilder.newBuilder("rackspace-cloudblockstorage-us")
      .credentials("{username}", "{apiKey}")
      .buildApi(CinderApi.class);

  // jclouds refers to "regions" as "zones"
  VolumeApi volumeApi = cinderApi.getVolumeApiForZone("{region}");
  SnapshotApi snapshotApi = cinderApi.getSnapshotApiForZone("{region}");

.. code-block:: javascript

  pkgcloud = require('pkgcloud');

  // each client is bound to a specific service and provider
  var client = pkgcloud.blockstorage.createClient({
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

  $volumeService = $client->volumeService();

.. code-block:: python

  import pyrax
  pyrax.set_credentials("{username}", "{apiKey}", region="{region}")
  cbs = pyrax.cloud_blockstorage

.. code-block:: ruby

  require 'fog'

  @client = Fog::Rackspace::BlockStorage.new(
    :rackspace_username => '{username}',
    :rackspace_api_key => '{apiKey}',
    :rackspace_region => '{region}'
  )

.. code-block:: sh

  # {username}, {apiKey} below are placeholders, do not enclose '{}' when you replace them with actual credentials.

  curl -s -X POST https://identity.api.rackspacecloud.com/v2.0/tokens \
    -H "Content-Type: application/json" \
    -d '{
      "auth": {
        "RAX-KSKEY:apiKeyCredentials": {
          "username": "{username}",
          "apiKey": "{apiKey}"
        }
      }
    }' | python -m json.tool

  # From the resulting json, set two environment variables: TOKEN and ENDPOINT.

  export TOKEN="{tokenId}"
  export ENDPOINT="{publicUrl}" # For Block Storage service
