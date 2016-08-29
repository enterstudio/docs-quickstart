.. code-block:: csharp

  cloudFilesProvider.CreateObjectFromFile("{container_name}", "{path_to_file}", "{subdirectories}/{object_name}");

.. code-block:: go

  f, err := os.Open("{pathToFile}")
  defer f.Close()
  reader := bufio.NewReader(f)

  _, err := objects.Create(
    serviceClient,
    "{containerName}",
    "{subdirectories}/{objectName}",
    reader,
    nil,
  ).ExtractHeader()

.. code-block:: java

  ObjectApi objectApi =
      cloudFilesApi.getObjectApiForRegionAndContainer("{region}", "{containerName}");

  // Upload a File
  ByteSource byteSource = Files.asByteSource(new File("{filePath}"));
  Payload filePayload = Payloads.newByteSourcePayload(byteSource);
  objectApi.put("{subdirectories}/{objectName}", filePayload);

.. code-block:: javascript

  // we need to use the fs module to access the local disk
  var fs = require('fs');

  // TODO use a real file here
  var filePath = '{path_to_file}';

  // create a read stream for our source file
  var source = fs.createReadStream(filePath);

  // create a writeable stream for our destination
  var dest = client.upload({
    container: 'sample-container-test',
    remote: '{subdirectories}/{objectName}'
  });

  dest.on('error', function(err) {
    // TODO handle err as appropriate
  });

  dest.on('success', function(file) {
    // TODO handle successful upload case
  });

  // pipe the source to the destination
  source.pipe(dest);

.. code-block:: php

  // Upload an object to the container.
  $localFileName  = '{path_to_file}';
  $remoteFileName = '{subdirectories}/{object_name}';

  $handle = fopen($localFileName, 'r');
  $object = $container->uploadObject($remoteFileName, $handle);

  // Note that while we call fopen to open the file resource, we do not call fclose at the end.
  // The file resource is automatically closed inside the uploadObject call.

.. code-block:: python

  container = pyrax.cloudfiles.create_container("gallery")
  obj = container.store_object("{subdirectories}/{object_name}", data)

.. code-block:: ruby

  # :body can also be an open IO object like a File, to stream content instead
  # of providing it all at once.

  file = directory.files.create(
    :key => '{subdirectories}/{object_name}',
    :body => 'Rackspace is awesome!'
  )

.. code-block:: sh

  curl -i -X PUT $ENDPOINT/{containerName}/{subdirectories}/{objectName} /
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: image/jpeg" \
    -H "Content-Length: 0"
