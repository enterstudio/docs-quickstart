.. code-block:: csharp

  FileStream fileStream = new FileStream("/tmp/somefile.txt", FileMode.Open, FileAccess.Read);
  int fileLength = (int)fileStream.Length;
  byte[] buffer = new byte[fileLength];
  int nbrOfBytes;
  int bytesRead = 0;
  while ((nbrOfBytes = fileStream.Read(buffer, bytesRead, fileLength - bytesRead)) > 0)
      bytesRead += nbrOfBytes;
  fileStream.Close();
  using (fileStream)
  {
      cloudFilesProvider.CreateObject("example_container", fileStream, "someobject");
  }

  // OR, much simpler...
  // cloudFilesProvider.CreateObjectFromFile("example_container", "/tmp/somefile.txt", "someobject");

.. code-block:: java

  // create a payload
  Payload payload = Payloads.newByteSourcePayload(ByteSource.wrap("sample-data".getBytes()));

  ObjectApi objectApi = cloudFilesApi.getObjectApiForRegionAndContainer("{region}", "example_container")
  objectApi.put("someobject", payload);

.. code-block:: javascript

  // we need to use the fs module to access the local disk
  var fs = require('fs');

  // TODO use a real file here
  var filePath = '/tmp/somefile.txt';

  // create a read stream for our source file
  var source = fs.createReadStream(filePath);

  // create a writeable stream for our destination
  var dest = client.upload({
    container: 'example_container',
    remote: 'someobject'
  }, function(err) {
    if (err) {
      // TODO handle as appropriate
    }
  });

  // pipe the source to the destination
  source.pipe(dest);

.. code-block:: php

  // Upload an object to the container.
  $localFileName  = __DIR__ . '/php-elephant.jpg';
  $remoteFileName = 'php-elephant.jpg';

  $handle = fopen($localFileName, 'r');
  $object = $container->uploadObject($remoteFileName, $handle);

  // Note that while we call fopen to open the file resource, we do not call fclose at the end.
  // The file resource is automatically closed inside the uploadObject call.

.. code-block:: python

  obj = container.store_object("someobject", data)

.. code-block:: ruby

  # :body can also be an open IO object like a File, to stream content instead
  # of providing it all at once.

  file = directory.files.create(
    :key => 'somefile.txt',
    :body => 'Rackspace is awesome!'
  )

.. code-block:: sh

  curl -i -X PUT $ENDPOINT/{containerName}/{objectName} /
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: image/jpeg" \
    -H "Content-Length: 0"
