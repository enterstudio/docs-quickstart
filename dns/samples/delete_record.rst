.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

  rackspace.deleteRecord(myZone, myRec, function (err){
    if (err) {
      console.dir(err);
      return;
    }
    console.log('DNS Record was successfully deleted.');
  });

.. code-block:: php

    $record->delete();

.. code-block:: python

   record.delete()

.. code-block:: ruby

   record.destroy
