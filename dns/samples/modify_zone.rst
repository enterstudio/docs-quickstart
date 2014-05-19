.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

	myZone.emailAddress = 'changed@domain.com';
  rackspace.updateZone(myZone, function (err) {
    if (err) {
      console.dir(err);
      return;
    }
    console.log('Zone was successfully modified');
  });

.. code-block:: php

    // Specify your changes
    $changes = array(
        'email' => 'new_dev@domain.com',
        'ttl'   => 3600
    );

    $domain->update($changes);

.. code-block:: python

	domain.update(emailAddress="new_dev@domain.com")

.. code-block:: ruby

    zone.email = 'changed@domain.com'
    zone.ttl = 3600
    zone.save

.. code-block:: shell

.. code-block:: shell

  $ curl -X PUT -d \
    '{
        "comment" : "{updatedComment}",
        "ttl" : 300,
        "emailAddress" : "{updatedEMailAddress}"
    }' \
    -H "X-Auth-Token: $TOKEN" \
    -H 'Content-Type: application/json' \
    $ENDPOINT/domains | python -m json.tool