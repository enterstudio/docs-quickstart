.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

    # To create a snapshot for a volume, the volume should be detached from
    # any server. You must supply a name for the snapshot, and may provide
    # an optional description.
    snap = vol.create_snapshot({name}, {description})

.. code-block:: ruby

  snapshot = volume.create_snapshot
