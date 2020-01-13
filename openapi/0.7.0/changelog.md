Changelog
=========

Version 0.6.0 to 0.7.0

Changes
-------

### MV Sense

**Returns all configured analytic zones for this camera**

#### GET _`/devices/{serial}/camera/analytics/zones`_

> Response property `regionOfInterest` value added:
> 
>            
>       {
>         regionOfInterest: {"x0":"0.00","y0":"0.00","x1":"1.00","y1":"1.00"}
>       }
>     

* * *

### SM

**Get the profiles associated with a user**

#### GET _`/networks/{networkId}/sm/user/{userId}/deviceProfiles`_

> Response property `deviceId` value added:
> 
>            
>       {
>         deviceId: "1234"
>       }
>     

* * *

**Get a list of softwares associated with a user**

#### GET _`/networks/{networkId}/sm/user/{userId}/softwares`_

> Response property `deviceId` value added:
> 
>            
>       {
>         deviceId: "1234"
>       }
>     

* * *

**List the certs on a device**

#### GET _`/networks/{networkId}/sm/{deviceId}/certs`_

> Response property `deviceId` value added:
> 
>            
>       {
>         deviceId: "1234"
>       }
>     

* * *

**Get the profiles associated with a device**

#### GET _`/networks/{networkId}/sm/{deviceId}/deviceProfiles`_

> Response property `deviceId` value added:
> 
>            
>       {
>         deviceId: "1234"
>       }
>     

* * *

**Get a list of softwares associated with a device**

#### GET _`/networks/{networkId}/sm/{deviceId}/softwares`_

> Response property `deviceId` value added:
> 
>            
>       {
>         deviceId: "1234"
>       }
>     

* * *

### Switch settings

**Return the storm control configuration for a switch network**

#### GET _`/networks/{networkId}/switch/settings/stormControl`_

> Summary changed from `Return the global enhanced storm control configuration` to `Return the storm control configuration for a switch network`

* * *

**Update the storm control configuration for a switch network**

#### PUT _`/networks/{networkId}/switch/settings/stormControl`_

> Summary changed from `Update the global enhanced storm control configuration` to `Update the storm control configuration for a switch network`

* * *

### Wireless settings

**Update the wireless settings for a network**

#### PUT _`/networks/{networkId}/wireless/settings`_

> Optional property `ledLightsOn` Added

* * *

### Devices

**List the devices in an organization**

#### GET _`/organizations/{organizationId}/devices`_

> Optional param `configurationUpdatedAfter` added

* * *

### Cameras

#### PATH _`/devices/{serial}/camera/qualityAndRetentionSettings`_

> New Endpoint  
> 
> ### Returns quality and retention settings for the given camera
> 
> **(GET)** _getDeviceCameraQualityAndRetentionSettings_
> 
>     {
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "restrictedBandwidthModeEnabled": false,
>         "profileId": null,
>         "quality": "Standard",
>         "resolution": 720
>     }
> 
>   
> 
> ### Update quality and retention settings for the given camera
> 
> **(PUT)** _updateDeviceCameraQualityAndRetentionSettings_
> 
>     {
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "restrictedBandwidthModeEnabled": false,
>         "profileId": null,
>         "quality": "Standard",
>         "resolution": 720
>     }

* * *

#### PATH _`/networks/{networkId}/camera/schedules`_

> New Endpoint  
> 
> ### Returns a list of all camera recording schedules.
> 
> **(GET)** _getNetworkCameraSchedules_
> 
>     [
>         {
>             "id": "123",
>             "name": "Weekday schedule"
>         },
>         {
>             "id": "124",
>             "name": "Office hours"
>         }
>     ]

* * *

### MG LAN settings

#### PATH _`/devices/{serial}/cellularGateway/settings`_

> New Endpoint  
> 
> ### Show the LAN Settings of a MG
> 
> **(GET)** _getDeviceCellularGatewaySettings_
> 
>     {
>         "deviceName": "name of the MG",
>         "deviceLanIp": "192.168.0.33",
>         "deviceSubnet": "192.168.0.32/27",
>         "fixedIpAssignments": [
>             {
>                 "mac": "0b:00:00:00:00:ac",
>                 "name": "server 1",
>                 "ip": "192.168.0.10"
>             },
>             {
>                 "mac": "0b:00:00:00:00:ab",
>                 "name": "server 2",
>                 "ip": "192.168.0.20"
>             }
>         ],
>         "reservedIpRanges": [
>             {
>                 "start": "192.168.1.0",
>                 "end": "192.168.1.1",
>                 "comment": "A reserved IP range"
>             }
>         ]
>     }
> 
>   
> 
> ### Update the LAN Settings for a single MG.
> 
> **(PUT)** _updateDeviceCellularGatewaySettings_
> 
>     {
>         "deviceName": "name of the MG",
>         "deviceLanIp": "192.168.0.33",
>         "deviceSubnet": "192.168.0.32/27",
>         "fixedIpAssignments": [
>             {
>                 "mac": "0b:00:00:00:00:ac",
>                 "name": "server 1",
>                 "ip": "192.168.0.10"
>             },
>             {
>                 "mac": "0b:00:00:00:00:ab",
>                 "name": "server 2",
>                 "ip": "192.168.0.20"
>             }
>         ],
>         "reservedIpRanges": [
>             {
>                 "start": "192.168.1.0",
>                 "end": "192.168.1.1",
>                 "comment": "A reserved IP range"
>             }
>         ]
>     }

* * *

### MG port forwarding rules

#### PATH _`/devices/{serial}/cellularGateway/settings/portForwardingRules`_

> New Endpoint  
> 
> ### Returns the port forwarding rules for a single MG.
> 
> **(GET)** _getDeviceCellularGatewaySettingsPortForwardingRules_
> 
>     {
>         "rules": [
>             {
>                 "lanIp": "172.31.128.5",
>                 "name": "test",
>                 "access": "any",
>                 "publicPort": "11-12",
>                 "localPort": "4",
>                 "uplink": "both",
>                 "protocol": "tcp"
>             },
>             {
>                 "lanIp": "172.31.128.5",
>                 "name": "test 2",
>                 "access": "restricted",
>                 "allowedIps": [
>                     "10.10.10.10",
>                     "10.10.10.11"
>                 ],
>                 "publicPort": "99",
>                 "localPort": "5",
>                 "uplink": "both",
>                 "protocol": "tcp"
>             }
>         ]
>     }
> 
>   
> 
> ### Updates the port forwarding rules for a single MG.
> 
> **(PUT)** _updateDeviceCellularGatewaySettingsPortForwardingRules_
> 
>     {
>         "rules": [
>             {
>                 "lanIp": "172.31.128.5",
>                 "name": "test",
>                 "access": "any",
>                 "publicPort": "11-12",
>                 "localPort": "4",
>                 "uplink": "both",
>                 "protocol": "tcp"
>             },
>             {
>                 "lanIp": "172.31.128.5",
>                 "name": "test 2",
>                 "access": "restricted",
>                 "allowedIps": [
>                     "10.10.10.10",
>                     "10.10.10.11"
>                 ],
>                 "publicPort": "99",
>                 "localPort": "5",
>                 "uplink": "both",
>                 "protocol": "tcp"
>             }
>         ]
>     }

* * *

### Switch ports

#### PATH _`/devices/{serial}/switchPortStatuses`_

> New Endpoint  
> 
> ### Return the status for all the ports of a switch
> 
> **(GET)** _getDeviceSwitchPortStatuses_
> 
>     [
>         {
>             "portId": "1",
>             "enabled": true,
>             "status": "Connected",
>             "errors": [
>                 "PoE overload",
>                 "Very high proportion of CRC errors"
>             ],
>             "warnings": [
>                 "PoE port was denied power",
>                 "High proportion of CRC errors"
>             ],
>             "speed": "10 Gbps",
>             "duplex": "full",
>             "usageInKb": {
>                 "total": 40867,
>                 "sent": 23008,
>                 "recv": 17859
>             },
>             "cdp": {
>                 "systemName": "",
>                 "platform": "MS350-24X",
>                 "deviceId": "0c8ddbddee:ff",
>                 "portId": "Port 20",
>                 "nativeVlan": 1,
>                 "address": "10.0,0.1",
>                 "managementAddress": "10.0.0.100",
>                 "version": "1",
>                 "vtpManagementDomain": "",
>                 "capabilities": "Switch"
>             },
>             "lldp": {
>                 "systemName": "MS350-24X - Test",
>                 "systemDescription": "MS350-24X Cloud Managed PoE Switch",
>                 "portId": "20",
>                 "portDescription": "Port 20",
>                 "chassisId": "0c:8d:db:dd:ee:ff",
>                 "managementVlan": 1,
>                 "portVlan": 1,
>                 "managementAddress": "10.0.0.100",
>                 "systemCapabilities": "switch"
>             },
>             "clientCount": 10
>         }
>     ]

* * *

### MX inbound firewall

#### PATH _`/networks/{networkId}/appliance/firewall/inboundFirewallRules`_

> New Endpoint  
> 
> ### Return the inbound firewall rules for an MX network
> 
> **(GET)** _getNetworkApplianceFirewallInboundFirewallRules_
> 
>     {
>         "rules": [
>             {
>                 "comment": "Allow TCP traffic to subnet with HTTP servers.",
>                 "policy": "allow",
>                 "protocol": "tcp",
>                 "destPort": 443,
>                 "destCidr": "192.168.1.0/24",
>                 "srcPort": "Any",
>                 "srcCidr": "Any",
>                 "syslogEnabled": false
>             }
>         ],
>         "syslogDefaultRule": true
>     }
> 
>   
> 
> ### Update the inbound firewall rules of an MX network
> 
> **(PUT)** _updateNetworkApplianceFirewallInboundFirewallRules_
> 
>     {
>         "rules": [
>             {
>                 "comment": "Allow TCP traffic to subnet with HTTP servers.",
>                 "policy": "allow",
>                 "protocol": "tcp",
>                 "destPort": 443,
>                 "destCidr": "192.168.1.0/24",
>                 "srcPort": "Any",
>                 "srcCidr": "Any",
>                 "syslogEnabled": false
>             }
>         ],
>         "syslogDefaultRule": true
>     }

* * *

### Camera quality retention profiles

#### PATH _`/networks/{networkId}/camera/qualityRetentionProfiles`_

> New Endpoint  
> 
> ### List the quality retention profiles for this network
> 
> **(GET)** _getNetworkCameraQualityRetentionProfiles_
> 
>     [
>         {
>             "id": "1234",
>             "networkId": "N_24329156",
>             "name": "Sample quality retention profile",
>             "restrictedBandwidthModeEnabled": true,
>             "motionBasedRetentionEnabled": false,
>             "audioRecordingEnabled": false,
>             "cloudArchiveEnabled": false,
>             "maxRetentionDays": 7,
>             "scheduleId": null,
>             "videoSettings": {
>                 "MV32": {
>                     "quality": "Enhanced",
>                     "resolution": "1080x1080"
>                 },
>                 "MV21/MV71": {
>                     "quality": "High",
>                     "resolution": "1280x720"
>                 },
>                 "MV12/MV22/MV72": {
>                     "quality": "High",
>                     "resolution": "1920x1080"
>                 },
>                 "MV12WE": {
>                     "quality": "High",
>                     "resolution": "1920x1080"
>                 }
>             }
>         }
>     ]
> 
>   
> 
> ### Creates new quality retention profile for this network.
> 
> **(POST)** _createNetworkCameraQualityRetentionProfile_
> 
>     {
>         "id": "1234",
>         "networkId": "N_24329156",
>         "name": "Sample quality retention profile",
>         "restrictedBandwidthModeEnabled": true,
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "cloudArchiveEnabled": false,
>         "maxRetentionDays": 7,
>         "scheduleId": null,
>         "videoSettings": {
>             "MV32": {
>                 "quality": "Enhanced",
>                 "resolution": "1080x1080"
>             },
>             "MV21/MV71": {
>                 "quality": "High",
>                 "resolution": "1280x720"
>             },
>             "MV12/MV22/MV72": {
>                 "quality": "High",
>                 "resolution": "1920x1080"
>             },
>             "MV12WE": {
>                 "quality": "High",
>                 "resolution": "1920x1080"
>             }
>         }
>     }

* * *

#### PATH _`/networks/{networkId}/camera/qualityRetentionProfiles/{qualityRetentionProfileId}`_

> New Endpoint  
> 
> ### Retrieve a single quality retention profile
> 
> **(GET)** _getNetworkCameraQualityRetentionProfile_
> 
>     {
>         "id": "1234",
>         "networkId": "N_24329156",
>         "name": "Sample quality retention profile",
>         "restrictedBandwidthModeEnabled": true,
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "cloudArchiveEnabled": false,
>         "maxRetentionDays": 7,
>         "scheduleId": null,
>         "videoSettings": {
>             "MV32": {
>                 "quality": "Enhanced",
>                 "resolution": "1080x1080"
>             },
>             "MV21/MV71": {
>                 "quality": "High",
>                 "resolution": "1280x720"
>             },
>             "MV12/MV22/MV72": {
>                 "quality": "High",
>                 "resolution": "1920x1080"
>             },
>             "MV12WE": {
>                 "quality": "High",
>                 "resolution": "1920x1080"
>             }
>         }
>     }
> 
>   
> 
> ### Update an existing quality retention profile for this network.
> 
> **(PUT)** _updateNetworkCameraQualityRetentionProfile_
> 
>     {
>         "id": "1234",
>         "networkId": "N_24329156",
>         "name": "Sample quality retention profile",
>         "restrictedBandwidthModeEnabled": true,
>         "motionBasedRetentionEnabled": false,
>         "audioRecordingEnabled": false,
>         "cloudArchiveEnabled": false,
>         "maxRetentionDays": 7,
>         "scheduleId": null,
>         "videoSettings": {
>             "MV32": {
>                 "quality": "Enhanced",
>                 "resolution": "1080x1080"
>             },
>             "MV21/MV71": {
>                 "quality": "High",
>                 "resolution": "1280x720"
>             },
>             "MV12/MV22/MV72": {
>                 "quality": "High",
>                 "resolution": "1920x1080"
>             },
>             "MV12WE": {
>                 "quality": "High",
>                 "resolution": "1920x1080"
>             }
>         }
>     }
> 
>   
> 
> ### Delete an existing quality retention profile for this network.
> 
> **(DELETE)** _deleteNetworkCameraQualityRetentionProfile_

* * *

### MG connectivity monitoring destinations

#### PATH _`/networks/{networkId}/cellularGateway/settings/connectivityMonitoringDestinations`_

> New Endpoint  
> 
> ### Return the connectivity testing destinations for an MG network
> 
> **(GET)** _getNetworkCellularGatewaySettingsConnectivityMonitoringDestinations_
> 
>     {
>         "destinations": [
>             {
>                 "ip": "8.8.8.8",
>                 "description": "Google",
>                 "default": false
>             },
>             {
>                 "ip": "1.23.45.67",
>                 "description": "test description",
>                 "default": true
>             },
>             {
>                 "ip": "9.8.7.6",
>                 "description": null,
>                 "default": false
>             }
>         ]
>     }
> 
>   
> 
> ### Update the connectivity testing destinations for an MG network
> 
> **(PUT)** _updateNetworkCellularGatewaySettingsConnectivityMonitoringDestinations_
> 
>     {
>         "destinations": [
>             {
>                 "ip": "8.8.8.8",
>                 "description": "Google",
>                 "default": false
>             },
>             {
>                 "ip": "1.23.45.67",
>                 "description": "test description",
>                 "default": true
>             },
>             {
>                 "ip": "9.8.7.6",
>                 "description": null,
>                 "default": false
>             }
>         ]
>     }

* * *

### MG DHCP settings

#### PATH _`/networks/{networkId}/cellularGateway/settings/dhcp`_

> New Endpoint  
> 
> ### List common DHCP settings of MGs
> 
> **(GET)** _getNetworkCellularGatewaySettingsDhcp_
> 
>     {
>         "dhcpLeaseTime": "1 hour",
>         "dnsNameservers": "custom",
>         "dnsCustomNameservers": [
>             "172.16.2.111",
>             "172.16.2.30"
>         ]
>     }
> 
>   
> 
> ### Update common DHCP settings of MGs
> 
> **(PUT)** _updateNetworkCellularGatewaySettingsDhcp_
> 
>     {
>         "dhcpLeaseTime": "1 hour",
>         "dnsNameservers": "custom",
>         "dnsCustomNameservers": [
>             "172.16.2.111",
>             "172.16.2.30"
>         ]
>     }

* * *

### MG subnet pool settings

#### PATH _`/networks/{networkId}/cellularGateway/settings/subnetPool`_

> New Endpoint  
> 
> ### Return the subnet pool and mask configured for MGs in the network.
> 
> **(GET)** _getNetworkCellularGatewaySettingsSubnetPool_
> 
>     {
>         "cidr": "192.168.0.0/16",
>         "mask": "24",
>         "subnets": [
>             {
>                 "serial": "AAAA-AAAA-AAAA",
>                 "name": "my first MG",
>                 "applianceIp": "192.168.0.1",
>                 "subnet": "192.168.0.0/24"
>             },
>             {
>                 "serial": "BBBB-BBBB-BBBB",
>                 "name": "my second MG",
>                 "applianceIp": "192.168.0.33",
>                 "subnet": "192.168.0.32/24"
>             }
>         ]
>     }
> 
>   
> 
> ### Update the subnet pool and mask configuration for MGs in the network.
> 
> **(PUT)** _updateNetworkCellularGatewaySettingsSubnetPool_
> 
>     {
>         "cidr": "192.168.0.0/16",
>         "mask": "24",
>         "subnets": [
>             {
>                 "serial": "AAAA-AAAA-AAAA",
>                 "name": "my first MG",
>                 "applianceIp": "192.168.0.1",
>                 "subnet": "192.168.0.0/24"
>             },
>             {
>                 "serial": "BBBB-BBBB-BBBB",
>                 "name": "my second MG",
>                 "applianceIp": "192.168.0.33",
>                 "subnet": "192.168.0.32/24"
>             }
>         ]
>     }

* * *

### MG uplink settings

#### PATH _`/networks/{networkId}/cellularGateway/settings/uplink`_

> New Endpoint  
> 
> ### Returns the uplink settings for your MG network.
> 
> **(GET)** _getNetworkCellularGatewaySettingsUplink_
> 
>     {
>         "bandwidthLimits": {
>             "limitUp": 51200,
>             "limitDown": 51200
>         }
>     }
> 
>   
> 
> ### Updates the uplink settings for your MG network.
> 
> **(PUT)** _updateNetworkCellularGatewaySettingsUplink_
> 
>     {
>         "bandwidthLimits": {
>             "limitUp": 51200,
>             "limitDown": 51200
>         }
>     }

* * *

### Link aggregations

#### PATH _`/networks/{networkId}/switch/linkAggregations`_

> New Endpoint  
> 
> ### List link aggregation groups
> 
> **(GET)** _getNetworkSwitchLinkAggregations_
> 
>     [
>         {
>             "id": "NDU2N18yXzM=",
>             "switchPorts": [
>                 {
>                     "serial": "Q234-ABCD-0001",
>                     "portId": "1"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0002",
>                     "portId": "2"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0003",
>                     "portId": "3"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0004",
>                     "portId": "4"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0005",
>                     "portId": "5"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0006",
>                     "portId": "6"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0007",
>                     "portId": "7"
>                 },
>                 {
>                     "serial": "Q234-ABCD-0008",
>                     "portId": "8"
>                 }
>             ]
>         }
>     ]
> 
>   
> 
> ### Create a link aggregation group
> 
> **(POST)** _createNetworkSwitchLinkAggregation_
> 
>     {
>         "id": "NDU2N18yXzM=",
>         "switchPorts": [
>             {
>                 "serial": "Q234-ABCD-0001",
>                 "portId": "1"
>             },
>             {
>                 "serial": "Q234-ABCD-0002",
>                 "portId": "2"
>             },
>             {
>                 "serial": "Q234-ABCD-0003",
>                 "portId": "3"
>             },
>             {
>                 "serial": "Q234-ABCD-0004",
>                 "portId": "4"
>             },
>             {
>                 "serial": "Q234-ABCD-0005",
>                 "portId": "5"
>             },
>             {
>                 "serial": "Q234-ABCD-0006",
>                 "portId": "6"
>             },
>             {
>                 "serial": "Q234-ABCD-0007",
>                 "portId": "7"
>             },
>             {
>                 "serial": "Q234-ABCD-0008",
>                 "portId": "8"
>             }
>         ]
>     }

* * *

#### PATH _`/networks/{networkId}/switch/linkAggregations/{linkAggregationId}`_

> New Endpoint  
> 
> ### Update a link aggregation group
> 
> **(PUT)** _updateNetworkSwitchLinkAggregation_
> 
>     {
>         "id": "NDU2N18yXzM=",
>         "switchPorts": [
>             {
>                 "serial": "Q234-ABCD-0001",
>                 "portId": "1"
>             },
>             {
>                 "serial": "Q234-ABCD-0002",
>                 "portId": "2"
>             },
>             {
>                 "serial": "Q234-ABCD-0003",
>                 "portId": "3"
>             },
>             {
>                 "serial": "Q234-ABCD-0004",
>                 "portId": "4"
>             },
>             {
>                 "serial": "Q234-ABCD-0005",
>                 "portId": "5"
>             },
>             {
>                 "serial": "Q234-ABCD-0006",
>                 "portId": "6"
>             },
>             {
>                 "serial": "Q234-ABCD-0007",
>                 "portId": "7"
>             },
>             {
>                 "serial": "Q234-ABCD-0008",
>                 "portId": "8"
>             }
>         ]
>     }
> 
>   
> 
> ### Split a link aggregation group into separate ports
> 
> **(DELETE)** _deleteNetworkSwitchLinkAggregation_

* * *