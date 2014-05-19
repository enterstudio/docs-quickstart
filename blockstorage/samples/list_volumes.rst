.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $volumes = $volumeService->volumeList();
    
.. code-block:: python

   vols = cbs.list()

.. code-block:: ruby

  @client.volumes.all

.. code-block:: shell

  $ curl -X GET $ENDPOINT/volumes \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" | python -m json.tool