.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  var cdnUrl = container.cdnUri + '/' + encodeURIComponent(file.name);

.. code-block:: php

  $cdnUrl = $object->getPublicUrl();

.. code-block:: python

  import urllib
  import urlparse
  encoded_name = urllib.quote(obj.name)
  cdn_url = urlparse.urljoin(container.cdn_uri, encoded_name)

.. code-block:: ruby

  file.public_url
  
.. code-block:: curl
    # To view CDN-enabled container details:
    $ curl -i -X HEAD $publicUrlCDN/{containerName} /
        -H "X-Auth-TOKEN: $TOKEN" 
    # NOTE: {containerName} is a placeholder: Replace it 
    # with an actual value and do not enclose it with {}.
