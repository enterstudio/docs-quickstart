.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

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

    @client = Fog::Rackspace::Queues.new(
      :rackspace_username => '{username}',
      :rackspace_api_key => '{apikey}',
      :rackspace_region => '{region}'
    )
