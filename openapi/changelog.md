Version 0.9.0
=========
*compared to **v0.8.0***

What's Changed
--------------

### \[ Clients \]

#### Provisions a client with a name and policy. Clients can be provisioned before they associate to the network.

POST _`/networks/{networkId}/clients/provision`_

> \- Property `groupPolicyId` type turn from `integer` to `string`

* * *

#### Update the policy assigned to a client on the network. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.

PUT _`/networks/{networkId}/clients/{clientId}/policy`_

> \- Property `devicePolicy` became required

> \- Param `updateNetworkClientPolicy` became required

* * *

#### Update a client's splash authorization. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.

PUT _`/networks/{networkId}/clients/{clientId}/splashAuthorizationStatus`_

> \- Property `ssids` became required

> \- Param `updateNetworkClientSplashAuthorizationStatus` became required

* * *

### \[ MX 1:1 NAT rules \]

#### Set the 1:1 NAT mapping rules for an MX network

PUT _`/networks/{networkId}/oneToOneNatRules`_

> \- Property `lanIp` became required

> \- Property `rules` became required

> \- Param `updateNetworkOneToOneNatRules` became required

* * *

### \[ MX port forwarding rules \]

#### Update the port forwarding rules for an MX network

PUT _`/networks/{networkId}/portForwardingRules`_

> \- Property `lanIp` became required

> \- Property `publicPort` became required

> \- Property `localPort` became required

> \- Property `allowedIps` became required

> \- Property `protocol` became required

> \- Property `rules` became required

> \- Param `updateNetworkPortForwardingRules` became required

* * *

### \[ Malware settings \]

#### Set the supported malware settings for an MX network

PUT _`/networks/{networkId}/security/malwareSettings`_

> \- Property `mode` became required

> \- Property `url` became required

> \- Property `comment` became required

> \- Property `sha256` became required

> \- Property `comment` became required

> \- Param `updateNetworkSecurityMalwareSettings` became required

* * *

### \[ MX static routes \]

#### Add a static route for an MX or teleworker network

POST _`/networks/{networkId}/staticRoutes`_

> \- Property `name` became required

> \- Property `subnet` became required

> \- Property `gatewayIp` became required

> \- Param `createNetworkStaticRoute` became required

* * *

### \[ Global \]

PATH _`/networks/{networkId}/staticRoutes/{srId}`_

> \- renamed to `/networks/{networkId}/staticRoutes/{staticRouteId}`

* * *

What's Updated
--------------

### \[ Clients \]

#### Provisions a client with a name and policy. Clients can be provisioned before they associate to the network.

POST _`/networks/{networkId}/clients/provision`_

> \- Optional property `policiesBySecurityAppliance` Added

> \- Optional property `policiesBySsid` Added

* * *

#### Update a client's splash authorization. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.

PUT _`/networks/{networkId}/clients/{clientId}/splashAuthorizationStatus`_

> \- Property `isAuthorized` Deleted

> \- Optional property `0` Added

> \- Optional property `1` Added

> \- Optional property `2` Added

> \- Optional property `3` Added

> \- Optional property `4` Added

> \- Optional property `5` Added

> \- Optional property `6` Added

> \- Optional property `7` Added

> \- Optional property `8` Added

> \- Optional property `9` Added

> \- Optional property `10` Added

> \- Optional property `11` Added

> \- Optional property `12` Added

> \- Optional property `13` Added

> \- Optional property `14` Added

* * *

### \[ MX 1:1 NAT rules \]

#### Set the 1:1 NAT mapping rules for an MX network

PUT _`/networks/{networkId}/oneToOneNatRules`_

> \- Property `protocol` Deleted

> \- Property `destinationPorts` Deleted

> \- Property `allowedIps` Deleted

* * *

### \[ Switch ports \]

#### Return the status for all the ports of a switch

GET _`/devices/{serial}/switchPortStatuses`_

> \- Response property `powerUsageInWh` value added

* * *

### \[ Camera quality retention profiles \]

#### Creates new quality retention profile for this network.

POST _`/networks/{networkId}/camera/qualityRetentionProfiles`_

> \- Optional property `MV22X/MV72X` Added

> \- Optional property `motionDetectorVersion` Added

* * *

#### Update an existing quality retention profile for this network.

PUT _`/networks/{networkId}/camera/qualityRetentionProfiles/{qualityRetentionProfileId}`_

> \- Optional property `MV22X/MV72X` Added

> \- Optional property `motionDetectorVersion` Added

* * *

#### List the quality retention profiles for this network

GET _`/networks/{networkId}/camera/qualityRetentionProfiles`_

> \- Response property `motionDetectorVersion` value added

* * *

#### Retrieve a single quality retention profile

GET _`/networks/{networkId}/camera/qualityRetentionProfiles/{qualityRetentionProfileId}`_

> \- Response property `motionDetectorVersion` value added

* * *

### \[ Cameras \]

#### Generate a snapshot of what the camera sees at the specified time and return a link to that image.

POST _`/networks/{networkId}/cameras/{serial}/snapshot`_

> \- Optional property `fullframe` Added

* * *

### \[ Devices \]

#### Claim devices into a network

POST _`/networks/{networkId}/devices/claim`_

> \- Optional property `serials` Added

> \- Summary changed from `Claim a device into a network` to `Claim devices into a network`

* * *

PATH _`/devices/{serial}/switch/ports/cycle`_

> \- Path added  
>   
> \- New endpoint
> 
> #### Cycle a set of switch ports
> 
> **POST** `/devices/{serial}/switch/ports/cycle`  
> 
>     {
>         "ports": [
>             "1",
>             "2-5",
>             "1_MA-MOD-8X10G_1",
>             "1_MA-MOD-8X10G_2-1_MA-MOD-8X10G_8"
>         ]
>     }
> 
> * * *

* * *

### \[ Switch settings \]

#### Return multicast settings for a network

GET _`/networks/{networkId}/switch/settings/multicast`_

> \- Summary changed from `Return Multicast settings for a network` to `Return multicast settings for a network`

* * *

### \[ Config templates \]

#### List the configuration templates for this organization

GET _`/organizations/{organizationId}/configTemplates`_

> \- Response property `productTypes` value added

* * *

### \[ Organizations \]

#### Return an overview of the license state for an organization

GET _`/organizations/{organizationId}/licenseState`_

> \- Summary changed from `Return the license state for an organization` to `Return an overview of the license state for an organization`

* * *

### \[ Bluetooth settings \]

PATH _`/devices/{serial}/wireless/bluetooth/settings`_

> \- Path added  
>   
> \- New endpoint
> 
> #### Return the bluetooth settings for a wireless device
> 
> **GET** `/devices/{serial}/wireless/bluetooth/settings`  
> 
>     {
>         "uuid": "00000000-0000-0000-000-000000000000",
>         "major": 13,
>         "minor": 125
>     }
> 
> * * *
> 
>   
> \- New endpoint
> 
> #### Update the bluetooth settings for a wireless device
> 
> **PUT** `/devices/{serial}/wireless/bluetooth/settings`  
> 
>     {
>         "uuid": "00000000-0000-0000-000-000000000000",
>         "major": 13,
>         "minor": 125
>     }
> 
> * * *

* * *

### \[ API usage \]

PATH _`/organizations/{organizationId}/apiRequests/overview`_

> \- Path added  
>   
> \- New endpoint
> 
> #### Return an aggregated overview of API requests data
> 
> **GET** `/organizations/{organizationId}/apiRequests/overview`  
> 
>     {
>         "responseCodeCounts": {
>             "200": 50000,
>             "201": 4000,
>             "204": 1000,
>             "400": 3500,
>             "404": 1500,
>             "429": 10000
>         }
>     }
> 
> * * *

* * *

### \[ Change log \]

PATH _`/organizations/{organizationId}/configurationChanges`_

> \- Path added  
>   
> \- New endpoint
> 
> #### View the Change Log for your organization
> 
> **GET** `/organizations/{organizationId}/configurationChanges`  
> 
>     [
>         {
>             "ts": "2018-02-11T00:00:00.090210Z",
>             "adminName": "Miles Meraki",
>             "adminEmail": "miles@meraki.com",
>             "adminId": "212406",
>             "page": "via API",
>             "label": "PUT /api/v1/organizations/2930418",
>             "oldValue": "{\"id\":\"2930418\",\"name\":\"My organization\",\"url\":\"https://dashboard.meraki.com/o/VjjsAd/manage/organization/overview\"}",
>             "newValue": "{\"id\":\"2930418\",\"name\":\"My organization changed\",\"url\":\"https://dashboard.meraki.com/o/VjjsAd/manage/organization/overview\"}"
>         }
>     ]
> 
> * * *

* * *
