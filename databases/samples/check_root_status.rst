.. code-block:: csharp


.. code-block:: java

    InstanceApi instanceApi = troveApi.getInstanceApiForZone("{region}");

    boolean rootedStatus = instanceApi.isRooted("{instanceId}");

.. code-block:: javascript


.. code-block:: php

    if (true === $instance->isRootEnabled()) {
        // yes it is
    }

.. code-block:: python

    root_enabled = cdb.root_user_status()

.. code-block:: ruby

    instance.root_user_enabled?
