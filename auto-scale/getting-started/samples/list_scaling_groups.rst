.. code-block:: csharp

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  Group group = groupApi.list();

.. code-block:: javascript

.. code-block:: php

    $groups = $service->groupList();

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    scaling_groups = au.list()

.. code-block:: ruby

  scaling_groups = service.groups

.. code-block:: sh

  $ curl -X GET -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    $ENDPOINT/groups | python -m json.tool