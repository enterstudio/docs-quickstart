.. code-block:: csharp

  FlavorId flavorId =  new FlavorId("{flavorId}");
  ImageId imageId = new ImageId("{imageId}");

  GroupConfiguration groupConfiguration = new GroupConfiguration(name: "My Scaling Group", cooldown: TimeSpan.FromSeconds(60), minEntities: 2, maxEntities: 5, metadata: new JObject());
  LaunchConfiguration launchConfiguration = new ServerLaunchConfiguration(new ServerLaunchArguments(new ServerArgument(flavorId, imageId, "My Server Name", null, null)));
  PolicyConfiguration[] policyConfigurations = { };
  ScalingGroupConfiguration configuration = new ScalingGroupConfiguration(groupConfiguration, launchConfiguration, policyConfigurations);
  ScalingGroup scalingGroup = await cloudAutoScaleProvider.CreateGroupAsync(configuration, CancellationToken.None);

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  GroupConfiguration groupConfiguration = GroupConfiguration.builder()
            .minEntities(2)
            .maxEntities(5)
            .cooldown(60)
            .name("My Scaling Group")
            .metadata(ImmutableMap.of("somekey", "somevalue"))
            .build();

  LaunchConfiguration launchConfiguration = LaunchConfiguration.builder()
            .loadBalancers(ImmutableList.of(LoadBalancer.builder().port(8080).id(9099).build()))
            .serverName("My Server Name")
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

  // Not currently supported by this SDK

.. code-block:: php

  $service = $client->autoscaleService(null, '{region}');

  $object = (object) array(
     // Config which determines the autoscale group's behaviour
     'groupConfiguration' => (object) array(
        'name'        => 'My Scaling Group',
        'minEntities' => 2,
        'maxEntities' => 5,
        'cooldown'    => 60
     ),
     // Specify what's going to launch - in this case a server
     'launchConfiguration' => (object) array(
        'type' => 'launch_server',
        'args' => (object) array(
           // Server properties
           'server' => (object) array(
              'flavorRef' => '{flavorId}',
              'name'      => 'My Server Name',
              'imageRef'  => '{imageId}'
           ),
           // LB properties
           'loadBalancer' => array(
              (object) array(
                 'loadBalancerId' => {loadBalancerId},
                 'port'           => 80
              )
           )
        )
     ),
     'scalingPolicies' => array(
        array(
           'name'     => 'scale up by 1',
           'change'   => 1,
           'cooldown' => 60,
           'type'     => 'webhook'
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
                            min_entities=2, max_entities=5,
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

  attributes = {
    :server_name => "My Server Name",
    :image => my_image,
    :flavor => 3,
    :networks => ['{publicNetworkUuid}', '{serviceNetworkUuid}'],
    :personality => [
      {
        "path" => "/etc/SomeFileName.txt",
        "contents" => "SomeBase64EncodedString"
      }
    ],
    :max_entities => 5,
    :min_entities => 2,
    :cooldown => 600,
    :name => "My Scaling Group",
    :metadata => { "created_by" => "autoscale sample script" },
    :load_balancers => {
       :port =>  80,
       :loadBalancerId => '{loadBalancerId}'
     }
    :launch_config_type => :launch_server
  }

  my_group = Fog::Rackspace::AutoScale::GroupBuilder.build(service, attributes)

.. code-block:: sh

  curl -X POST $ENDPOINT/groups \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" \
    -H "Content-Type: application/json" \
    -d '{
     "launchConfiguration": {
        "args": {
           "server": {
              "name": "My Server Name",
              "imageRef": "{imageId}",
              "flavorRef": "{flavorId}",
              "OS-DCF:diskConfig": "AUTO"
           }
        },
      "type": "launch_server"
       },
       "groupConfiguration": {
          "minEntities": 2,
          "maxEntities": 5,
          "cooldown": 60,
          "name": "My Scaling Group"
       },
       "scalingPolicies": [
          {
             "cooldown": 0,
             "name": "My Scaling Policy",
             "change": 1,
             "type": "schedule",
             "args": {
                "cron": "23 * * * *"
             }
          }
       ]
    }' | python -m json.tool
