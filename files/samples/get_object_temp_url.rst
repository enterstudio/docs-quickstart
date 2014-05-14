.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  // this is not supported with pkgcloud at this time

.. code-block:: php

  // First, you'll need to set the "temp url key" on your Account. This is an
  // arbitrary secret shared between Cloud Files and your application that's
  // used to validate temp url requests. You only need to do this once.
  $account = $objectStoreService->getAccount();
  $account->setTempUrlSecret();

  // Get a temporary URL that will expire in 3600 seconds (1 hour) from now
  // and only allow GET HTTP requests to it.
  $expirationTimeInSeconds = 3600;
  $httpMethodAllowed = 'GET';
  $tempUrl = $object->getTemporaryUrl($expirationTimeInSeconds, $httpMethodAllowed);

.. code-block:: python

  # First, you'll need to set the "temp url key" on your Account. This is an
  # arbitrary secret shared between Cloud Files and your application that's
  # used to validate temp url requests. You only need to do this once.

  # Let pyrax set the temp URL key for you
  pyrax.cloudfiles.set_temp_url_key()

  # Set your own
  # pyrax.cloudfiles.set_temp_url_key("jnRB6#1sduo8YGUF&%7r7guf6f")

  # Get a temporary URL that will expire in 1800 seconds
  temp_url = obj.get_temp_url(1800)

.. code-block:: ruby

  # First, you'll need to set the "temp url key" on your Account. This is an
  # arbitrary secret shared between Cloud Files and your application that's
  # used to validate temp url requests. You only need to do this once.

  account = @client.account
  account.meta_temp_url_key = 'super secret squirrels'
  account.save

  # Then, when you want to generate temp urls, pass it to the Fog::Storage
  # constructor as ":rackspace_temp_url_key":

  @client = Fog::Storage.new(
    :provider => 'rackspace',
    :rackspace_username => '{username}',
    :rackspace_api_key => '{apiKey}',
    :rackspace_region => '{region}',
    :rackspace_temp_url_key => 'super secret squirrels'
  )

  # Now, you can create a temporary url for any file you access from that
  # @client with the #url method. Its argument is the expiration time for
  # the generated URL, expressed as seconds since the epoch (1970-01-01 00:00).

  directory = @client.directories.get('sample-container-test')
  file = directory.files.get('somefile.txt')
  temp_url = file.url(Time.now.to_i + 600)
