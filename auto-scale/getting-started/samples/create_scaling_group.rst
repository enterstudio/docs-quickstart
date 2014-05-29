.. code-block:: csharp

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  GroupConfiguration groupConfiguration = GroupConfiguration.builder()
            .maxEntities(25)
            .cooldown(60)
            .name("{groupName}")
            .minEntities(5)
            .metadata(ImmutableMap.of("notes", "This is an autoscale group for examples"))
            .build();

  LaunchConfiguration launchConfiguration = LaunchConfiguration.builder()
            .loadBalancers(ImmutableList.of(LoadBalancer.builder().port(8080).id(9099).build()))
            .serverName("{serverName}")
            .serverImageRef("{imageId}")
            .serverFlavorRef("{flavorId}")
            .type(LaunchConfigurationType.LAUNCH_SERVER)
            .build();

  CreateScalingPolicy scalingPolicy = CreateScalingPolicy.builder()
            .cooldown(60)
            .type(ScalingPolicyType.WEBHOOK)
            .name(NAME)
            .targetType(ScalingPolicyTargetType.PERCENT_CHANGE)
            .target("1")
            .build();

  Group g = groupApi.create(groupConfiguration, launchConfiguration, ImmutableList.of(scalingPolicy));

.. code-block:: javascript

.. code-block:: php

    $service = $client->autoscaleService();

    $object = (object) array(
       // Config which determines the autoscale group's behaviour
       'groupConfiguration' => (object) array(
          'name'        => 'New autoscale group',
          'minEntities' => 5,
          'maxEntities' => 25,
          'cooldown'    => 60
       ),
       // Specify what's going to launch - in this case a server
       'launchConfiguration' => (object) array(
          'type' => 'launch_server',
          'args' => (object) array(
             // Server properties
             'server' => (object) array(
                'flavorRef' => '{flavorId}',
                'name'      => 'My server name',
                'imageRef'  => '{imageId}'
             ),
             // LB properties
             'loadBalancer' => array(
                (object) array(
                   'loadBalancerId' => '{loadBalancerId}',
                   'port'           => 80
                )
             )
          )
       )
    );

    $group = $service->group();
    $group->create($object);

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    networks = [pyrax.cloudnetworks.PUBLIC_NET_ID,
            pyrax.cloudnetworks.SERVICE_NET_ID]
    scaling_group = au.create("My Scaling Group", cooldown=60,
                              min_entities=2, max_entities=24,
                              launch_config_type="launch_server",
                              server_name="My Server Name",
                              image_id="{imageId}", flavor_id="{flavorId}",
                              disk_config="MANUAL",
                              metadata={"someKey": "someValue"},
                              personality=[{"contents": "SomeBase64EncodedString",
                                            "path": "/etc/SomeFileName.txt"}],
                              networks=networks,
                              load_balancers=("{loadBalancerId}", 80),
                              key_name="MySSHKeyName")

.. code-block:: ruby

    # A group builder is provided for your convenience.
    # For other options please refer to the fog docs

    require 'fog/rackspace/models/auto_scale/group_builder'

    INTERNET = '00000000-0000-0000-0000-000000000000'
    SERVICE_NET = '11111111-1111-1111-1111-111111111111'

    attributes = {
      :server_name => "testgroup",
      :image => my_image,
      :flavor => 3,
      :networks => [INTERNET, SERVICE_NET],
      :personality => [
        {
          "path" => "/root/.csivh",
          "contents" => "VGhpcyBpcyBhIHRlc3QgZmlsZS4="
        }
      ],
      :max_entities => 3,
      :min_entities => 2,
      :cooldown => 600,
      :name => "MyScalingGroup",
      :metadata => { "created_by" => "autoscale sample script" },
      :load_balancers => {
         :port =>  80,
         :loadBalancerId => 1234
       }
      :launch_config_type => :launch_server
    }

    my_group = Fog::Rackspace::AutoScale::GroupBuilder.build(service, attributes)

.. code-block:: sh

  $ curl -X POST -d \
    '{
     "launchConfiguration":{
        "args":{
           "server":{
              "name":"{serverName}",
              "imageRef":"7cf5ffc3-7b20-46fd-98e4-fefa9908d7e8",
              "flavorRef":"{serverFlavor}",
              "OS-DCF:diskConfig":"AUTO"
           }
        },
      "type":"launch_server"
       },
       "groupConfiguration":{
          "maxEntities":{maxServers},
          "cooldown":360,
          "name":"{scalingGroupName}",
          "minEntities":{minServers}
       },
       "scalingPolicies":[
          {
             "cooldown":0,
             "name":"{scalingPolicyName}",
             "change":1,
             "type":"schedule",
             "args":{
                "cron":"23 * * * *"
             }
          }
       ]
    }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    $ENDPOINT/groups | python -m json.tool
