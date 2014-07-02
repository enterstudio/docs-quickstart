.. code-block:: csharp

  await cloudMonitoringProvider.RemoveAlarmAsync({entity_id}, {alarm_id}, CancellationToken.None);

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

  $alarm->delete();

.. code-block:: python
  
  alarm.delete()

.. code-block:: ruby

  alarm.destroy

.. code-block:: sh

  $ curl -X DELETE $ENDPOINT/entities/{entityId}/alarms/{alarmId} \
    -H "X-Auth-Token: $TOKEN"
