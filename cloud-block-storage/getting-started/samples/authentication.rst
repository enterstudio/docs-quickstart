.. code-block:: csharp

  using net.openstack.Core.Domain;
  using net.openstack.Providers.Rackspace;
  
  namespace GettingStarted
  {
  	class Program
  	{
  		static void Main(string[] args)
  		{
  			CloudIdentity cid = new CloudIdentity()
  			{
  				APIKey = "apikey_goes_here",
  				Username = "username_goes_here"
  			};
  			CloudIdentityProvider cip = new CloudIdentityProvider(cid);
  			UserAccess ua = cip.Authenticate(cid);
  		}
  	}
  }
  
.. code-block:: java

  CinderApi cinderApi = ContextBuilder.newBuilder("rackspace-cloudblockstorage-us")
         .credentials("{username}", "{apiKey}")
         .buildApi(CinderApi.class);

  // jclouds refers to "regions" as "zones"
  VolumeApi volumeApi = cinderApi.getVolumeApiForZone("{region}");
  SnapshotApi snapshotApi = cinderApi.getSnapshotApiForZone("{region}");

.. code-block:: javascript

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

  $ curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
    -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"{username}", "apiKey":"{apiKey}"}}}' \
    -H "Content-Type: application/json" | python -m json.tool

  # From the resulting json, set three environment variables: tenant, TOKEN and endpoint

  export TENANT="{tenantId}"
  export TOKEN="{tokenId}"
  export ENDPOINT="{publicUrl}" # For Block Storage service
