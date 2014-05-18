.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  var details = {
  name: 'domain.com',
  email: 'admin@domain.com',
  ttl: 300,
  comment: 'root level for domain.com'
  };

  rackspace.createZone(details, function (err, zone) {
    if (err) {
      console.dir(err);
      return;
    }
    console.log(zone.id + ' ' + zone.name + ' ' + zone.ttl);
  });

.. code-block:: php

    $dnsService = $client->dnsService();

    $domain = $dnsService->domain();
    $domain->create(array(
        'name'         => 'domain.com',
        'emailAddress' => 'admin@domain.com',
        'ttl'          => 300,
        'comment'      => 'Root level for domain.com'
    ));

.. code-block:: python

  domain = pyrax.cloud_dns.create(name="domain.com",
                                  emailAddress="admin@domain.com",
                                  ttl=300)

.. code-block:: ruby

    zone = @client.zones.create(
      :domain => 'domain.com',
      :email => 'admin@domain.com',
      :ttl => 300,
      :comment => 'root level for domain.com'
    )

.. code-block:: shell

  $ curl -X POST -d \
    '{
        "domains" : [ {
            "name" : "domain.com",
            "comment" : "Optional domain comment...",
            "subdomains" : {
                "domains" : []
            },
            "ttl" : 300,
            "emailAddress" : "admin@domain.com"
    } ]
    }' \
    -H 'X-Auth-Token: $TOKEN' \
    -H 'Content-Type: application/json' \
    $ENDPOINT/domains | python -m json.tool