.. code-block:: php

    $computeService = $client->computeService('cloudServersOpenStack', 'DFW');

    // Retrieve servers using their UUIDs
    $serverOne = $computeService->server('e836fc4e-056d-4447-a80e-fefcaa640216');
    $serverTwo = $computeService->server('5399cd36-a23f-41a6-bdf7-20902aec0e74');