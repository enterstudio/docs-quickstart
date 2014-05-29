.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

    $zones = $service->getMonitoringZones();

.. code-block:: python

  zones = cm.list_monitoring_zones()

.. code-block:: ruby

  @client.list_monitoring_zones.body['values']

.. code-block:: sh

  $ curl -X GET $ENDPOINT/monitoring_zones \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
