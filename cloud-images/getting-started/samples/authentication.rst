.. code-block:: csharp

  // Not currently supported by this SDK

.. code-block:: java

  // Not currently supported by this SDK

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
  pyrax.set_credentials("{username}", "{apiKey}")

.. code-block:: ruby

  # Not currently supported by this SDK

.. code-block:: sh

  # To authenticate, use your Rackspace Cloud Account user name and API key:
  curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X POST \
      -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"{username}", "apiKey":"{apiKey}"}}}' \
      -H "Content-Type: application/json" | python -m json.tool

  # NOTE: {username} and {apiKey} are placeholders:
  # Replace them with actual values and do not enclose the values with {}.

  # Export the publicURL for cloudImages to the ENDPOINT variable,
  # and your authentication token to the TOKEN variable.
  export ENDPOINT="{publicUrl}" # For the Cloud Images service.
  export TOKEN="{token}"
