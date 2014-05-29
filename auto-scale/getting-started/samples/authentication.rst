.. code-block:: csharp

.. code-block:: java

  AutoscaleApi autoscaleApi = ContextBuilder.newBuilder("rackspace-autoscale-us")
            .credentials("{username}", "{apiKey}")
            .buildApi(AutoscaleApi.class);

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

  import pyrax

  pyrax.set_setting("identity_type", "rackspace")
  pyrax.set_default_region('{region}')
  pyrax.set_credentials('{username}', '{apiKey}')

.. code-block:: ruby

.. code-block:: sh

  $ curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
    -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"{username}", "apiKey":"{apiKey}"}}}' \
    -H "Content-Type: application/json" | python -m json.tool

  # From the resulting json, set three environment variables: tenant, TOKEN and endpoint

  export TENANT="{tenantId}"
  export TOKEN="{tokenId}"
  export ENDPOINT="{publicUrl}" # For Auto Scaling service(s)
