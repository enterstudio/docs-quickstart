.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

.. code-block:: ruby

  # :label is a String that's a friendly name for the notification.
  # :type is one of 'webhook', 'email', or 'pagerduty'.
  # :details is a :type-specific Hash of configuration options.
  notification = @client.notifications.create(
    :label => 'tell the world',
    :type => 'email',
    :details => { :address => '{emailAddress}' }
  )
