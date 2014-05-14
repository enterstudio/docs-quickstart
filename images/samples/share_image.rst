.. code-block:: php

    // Load your new flavor
    $newFlavor = $compute->flavor('{newFlavorId}');

    $server->resize($newFlavor);