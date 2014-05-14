.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

.. code-block:: ruby

  # To list known notification plans:

  @client.list_notification_plans.body['values']

  alarm = entity.alarms.create(
    :check => check,
    :notification_plan_id => '{notificationPlanId}'
  )
