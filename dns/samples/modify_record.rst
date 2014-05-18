.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  myRec.data = '192.168.1.1';
  rackspace.updateRecord(myZone, myRec, function (err){
    if (err) {
      console.dir(err);
      return;
    }
    console.log('Record ' + myRec.name + ' was successfully modified.');
  });

.. code-block:: php

	// Let's decrease its TTL by an hour:
	$record->ttl -= 60;

	// And change its data value:
	$record->data = '192.168.1.1';

	$record->update();

.. code-block:: python

  record.update(data="192.168.5.6")

.. code-block:: ruby

  # Let's decrease its TTL by an hour:
  record.ttl -= 60

  # And change its data value:
  record.value = '192.168.1.1'

  record.save

.. code-block:: shell

  $ curl -X PUT -d \
    '{
        "type" : "A",
        "data" : "{updatedIPv4Address}",
        "ttl" : 3600
    }' \
    -H 'X-Auth-Token: $TOKEN' \
    -H 'Content-Type: application/json' \
    $ENDPOINT/domains/{domainId}/records/{recordId} | python -m json.tool