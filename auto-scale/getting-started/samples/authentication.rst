.. code-block:: csharp

  CloudIdentity cloudIdentity = new CloudIdentity()
  {
      APIKey = "{apikey}",
      Username = "{username}"
  };
  CloudAutoScaleProvider cloudAutoScaleProvider = new CloudAutoScaleProvider(cloudIdentity, "{region}", null);

.. code-block:: java

  AutoscaleApi autoscaleApi = ContextBuilder.newBuilder("rackspace-autoscale-us")
            .credentials("{username}", "{apiKey}")
            .buildApi(AutoscaleApi.class);

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  require 'vendor/autoload.php';

  use OpenCloud\Rackspace;

  $client = new Rackspace(Rackspace::US_IDENTITY_ENDPOINT, array(
      'username' => '{username}',
      'apiKey'   => '{apiKey}'
  ));

.. code-block:: python

  import pyrax

  pyrax.set_setting("identity_type", "rackspace")
  pyrax.set_default_region('{region}')
  pyrax.set_credentials('{username}', '{apiKey}')

.. code-block:: ruby

  require 'fog'

  @client = Fog::Rackspace::AutoScale.new(
    :rackspace_username => '{username}',
    :rackspace_api_key => '{apiKey}',
    :rackspace_region => '{region}'
  )

.. code-block:: sh

  curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
    -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"{username}", "apiKey":"{apiKey}"}}}' \
    -H "Content-Type: application/json" | python -m json.tool

  # From the resulting json, set two environment variables: TOKEN and ENDPOINT.

  export TOKEN="{tokenId}"
  export ENDPOINT="{publicUrl}" # For Auto Scaling service(s)
