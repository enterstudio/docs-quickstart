.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

.. code-block:: python

.. code-block:: ruby

  # List available check types. Note the "id" of the one you want to use.
  @client.check_types.all

  # :type is the String ID of the check type you wish to create.
  # :target_hostname is the host to be monitored. :target_alias can be specified instead, if you have ip addresses
  #   configured in the entity.
  # :monitoring_zones_poll is an Array listing the String ids of the monitoring zones from which this check should be
  #   performed.
  check = entity.checks.create(
    :type => 'remote.ping',
    :target_hostname => 'sample.hostname.com',
    :monitoring_zones_poll => ['{monitoringZoneId}']
  )
