.. code-block:: csharp

  CloudFilesProvider cloudFilesProvider = new CloudFilesProvider(cloudIdentity);
  cloudFilesProvider.DisableCDNOnContainer("{container_name}");

.. code-block:: go

  opts := cdncontainers.EnableOpts{CDNEnabled: false}
  _, err := cdncontainers.Enable(cdnClient, "{containerName}", opts).ExtractHeader()

.. code-block:: java

  CDNApi cdnApi = cloudFilesApi.getCDNApiForRegion("{region}");

  cdnApi.disable("{containerName}");

.. code-block:: javascript

  container.disableCdn(function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

.. code-block:: php

  $container->disableCdn();

.. code-block:: python

  container.make_private()

.. code-block:: ruby

  directory.public = false
  directory.save

.. code-block:: sh

  curl -i -X POST $ENDPOINT/{containerName} /
    -H "X-Auth-Token: $TOKEN" \
    -H "X-CDN-Enabled: False"
