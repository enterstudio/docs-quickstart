.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

    $computeService = $client->computeService('cloudServersOpenStack', 'DFW');

    // Retrieve servers using their UUIDs
    $serverOne = $computeService->server('e836fc4e-056d-4447-a80e-fefcaa640216');
    $serverTwo = $computeService->server('5399cd36-a23f-41a6-bdf7-20902aec0e74');

.. code-block:: python

.. code-block:: ruby

  compute = Fog::Compute.new(
    :provider => 'rackspace',
    :rackspace_username => '{username}',
    :rackspace_api_key => '{apiKey}',
    :rackspace_region => '{region}'
  )

  @server_one = compute.servers.get('{serverId1}')
  @server_two = compute.servers.get('{serverId2}')
