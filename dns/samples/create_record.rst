.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  var recDetails = {
    name: 'subdomain',
    data: '127.0.0.1',
    type: 'A'
  };

  rackspace.createRecord(myZone, recDetails, function (err, rec) {
    if (err) {
      console.dir(err);
      return;
    }
    console.log('Record ' + rec.name + ' was successfully created.');
  });

.. code-block:: php

    // Add a CNAME record
    $record = $domain->record(array(
        'type' => 'CNAME',
        'name' => 'www.domain.com',
        'ttl'  => 3600,
        'data' => 'domain.com'
    ));

    $record->create();

.. code-block:: python

  domain.add_record({'type': 'A',
                     'name': 'app.domain.com',
                     'ttl': 3600,
                     'data': '192.168.1.1'})

.. code-block:: ruby

    record = zone.records.create(
      :name => 'subdomain',
      :value => '127.0.0.1',
      :type => 'A'
    )

.. code-block:: shell

  $ curl -X POST -s -d \
    '{
        "records": [
            {
                "name" : "app.domain.com",
                "type" : "A",
                "data" : "{IPv4Address}",
                "ttl" : 3600
            }
        ]
    }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    $ENDPOINT/domains/{domainId}/records | python -m json.tool