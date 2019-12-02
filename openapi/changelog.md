Meraki Dashboard API Changelog

Changelog
=========

Version 0.5.0 to 0.6.0

Changes
-------

### SAML roles

**Create a SAML role**

#### POST

`/organizations/{organizationId}/samlRoles`

> Response `200` Deleted

> Response property `201` value added:
> 
>            
>             {
>               201: {"description":"Successful operation","schema":{"type":"object","x-is-dynamic":true},"examples":{"application/json":{"id":"TEdJIEN1c3RvbWVy","role":"myrole","orgAccess":"none","networks":[{"id":"N_1234","access":"full"}],"tags":[{"tag":"west","access":"read-only"}]}}}
>             }
>     

* * *

### Switch ports

**List the switch ports for a switch**

#### GET

`/devices/{serial}/switchPorts`

> Response property `macWhitelist` value added:
> 
>            
>             {
>               macWhitelist: ["34:56:fe:ce:8e:a0","34:56:fe:ce:8e:a1"]
>             }
>     

> Response property `stormControlEnabled` value added:
> 
>            
>             {
>               stormControlEnabled: true
>             }
>     

* * *

**Return a switch port**

#### GET

`/devices/{serial}/switchPorts/{number}`

> Response property `macWhitelist` value added:
> 
>            
>             {
>               macWhitelist: ["34:56:fe:ce:8e:a0","34:56:fe:ce:8e:a1"]
>             }
>     

> Response property `stormControlEnabled` value added:
> 
>            
>             {
>               stormControlEnabled: true
>             }
>     

* * *

**Update a switch port**

#### PUT

`/devices/{serial}/switchPorts/{number}`

> Optional property `stormControlEnabled` Added

* * *

### Networks

**Combine multiple networks into a single network**

#### POST

`/organizations/{organizationId}/networks/combine`

> Optional property `enrollmentString` Added

* * *

**Return a network**

#### GET

`/networks/{networkId}`

> Response property `enrollmentString` value added:
> 
>            
>             {
>               enrollmentString: "long-island-office"
>             }
>     

* * *

**List the networks in an organization**

#### GET

`/organizations/{organizationId}/networks`

> Response property `enrollmentString` value added:
> 
>            
>             {
>               enrollmentString: "long-island-office"
>             }
>     

* * *

**Update a network**

#### PUT

`/networks/{networkId}`

> Optional property `enrollmentString` Added

* * *

### SM

**Get a list of softwares associated with a user**

#### GET

`/networks/{networkId}/sm/user/{userId}/softwares`

> Response property `appId` value added:
> 
>            
>             {
>               appId: "1234"
>             }
>     

* * *

**Get a list of softwares associated with a device**

#### GET

`/networks/{networkId}/sm/{deviceId}/softwares`

> Response property `appId` value added:
> 
>            
>             {
>               appId: "1234"
>             }
>     

* * *

### API usage

**List the API requests made by an organization**

#### GET

`/organizations/{organizationId}/apiRequests`

> Optional param `sourceIp` added

> Response property `sourceIp` value added:
> 
>            
>             {
>               sourceIp: "123.123.123.1"
>             }
>     

* * *

### Organizations

**Return the inventory for an organization**

#### GET

`/organizations/{organizationId}/inventory`

> Optional param `includeLicenseInfo` added

* * *

**Return the third party VPN peers for an organization**

#### GET

`/organizations/{organizationId}/thirdPartyVPNPeers`

> Response property `remoteId` value added:
> 
>            
>             {
>               remoteId: "miles@meraki.com"
>             }
>     

* * *

**Update the third party VPN peers for an organization**

#### PUT

`/organizations/{organizationId}/thirdPartyVPNPeers`

> Optional property `remoteId` Added

* * *

### Switch ACLs

#### PATH

`/networks/{networkId}/switch/accessControlLists`

> Path added  
> 
> GET
> 
> _getNetworkSwitchAccessControlLists_  
> **Return the access control lists for a MS network**
> 
>     {
>         "rules": [
>             {
>                 "comment": "Deny SSH",
>                 "policy": "deny",
>                 "ipVersion": "ipv4",
>                 "protocol": "tcp",
>                 "srcCidr": "10.1.10.0/24",
>                 "srcPort": "any",
>                 "dstCidr": "172.16.30/24",
>                 "dstPort": 22,
>                 "vlan": 10
>             },
>             {
>                 "comment": "Default rule",
>                 "policy": "allow",
>                 "ipVersion": "any",
>                 "protocol": "any",
>                 "srcCidr": "any",
>                 "srcPort": "any",
>                 "dstCidr": "any",
>                 "dstPort": "any",
>                 "vlan": "any"
>             }
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchAccessControlLists_  
> **Update the access control lists for a MS network**
> 
>     {
>         "rules": [
>             {
>                 "comment": "Deny SSH",
>                 "policy": "deny",
>                 "ipVersion": "ipv4",
>                 "protocol": "tcp",
>                 "srcCidr": "10.1.10.0/24",
>                 "srcPort": "any",
>                 "dstCidr": "172.16.30/24",
>                 "dstPort": 22,
>                 "vlan": 10
>             },
>             {
>                 "comment": "Default rule",
>                 "policy": "allow",
>                 "ipVersion": "any",
>                 "protocol": "any",
>                 "srcCidr": "any",
>                 "srcPort": "any",
>                 "dstCidr": "any",
>                 "dstPort": "any",
>                 "vlan": "any"
>             }
>         ]
>     }

* * *

### Switch settings

#### PATH

`/networks/{networkId}/switch/settings/dhcpServerPolicy`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsDhcpServerPolicy_  
> **Return the DHCP server policy**
> 
>     {
>         "defaultPolicy": "block",
>         "allowedServers": [
>             "00:50:56:00:00:01",
>             "00:50:56:00:00:02"
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchSettingsDhcpServerPolicy_  
> **Update the DHCP server policy**
> 
>     {
>         "defaultPolicy": "block",
>         "allowedServers": [
>             "00:50:56:00:00:01",
>             "00:50:56:00:00:02"
>         ]
>     }

* * *

#### PATH

`/networks/{networkId}/switch/settings/dscpToCosMappings`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsDscpToCosMappings_  
> **Return the DSCP to CoS mappings**
> 
>     {
>         "mappings": [
>             {
>                 "dscp": 1,
>                 "cos": 1,
>                 "title": "Video"
>             }
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchSettingsDscpToCosMappings_  
> **Update the DSCP to CoS mappings**
> 
>     {
>         "mappings": [
>             {
>                 "dscp": 1,
>                 "cos": 1,
>                 "title": "Video"
>             }
>         ]
>     }

* * *

### Licenses

#### PATH

`/organizations/{organizationId}/licenses`

> Path added  
> 
> GET
> 
> _getOrganizationLicenses_  
> **List the licenses for an organization**
> 
>     [
>         {
>             "id": "1234",
>             "licenseType": "MX64-ENT",
>             "licenseKey": "Z21234567890",
>             "orderNumber": "4C1234567",
>             "deviceSerial": "Q234-ABCD-5678",
>             "networkId": "N_24329156",
>             "state": "active",
>             "seatCount": null,
>             "totalDurationInDays": 425,
>             "durationInDays": 365,
>             "permanentlyQueuedLicenses": [
>                 {
>                     "id": "5678",
>                     "licenseType": "MX64-ENT",
>                     "licenseKey": "Z21234567890",
>                     "orderNumber": "4C1234567",
>                     "durationInDays": 60
>                 }
>             ],
>             "claimDate": "2019-08-29T12:40:10Z",
>             "activationDate": "2019-09-01T15:01:46Z",
>             "expirationDate": "2020-10-30T15:01:46Z"
>         }
>     ]

* * *

#### PATH

`/organizations/{organizationId}/licenses/assignSeats`

> Path added  
> 
> POST
> 
> _assignOrganizationLicensesSeats_  
> **Assign SM seats to a network. This will increase the managed SM device limit of the network**
> 
>     {
>         "resultingLicenses": [
>             {
>                 "id": "1234",
>                 "licenseType": "SME",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "deviceSerial": null,
>                 "networkId": "N_24329156",
>                 "state": "active",
>                 "seatCount": 25,
>                 "totalDurationInDays": 365,
>                 "durationInDays": 365,
>                 "permanentlyQueuedLicenses": [],
>                 "claimDate": "2019-08-29T12:40:10Z",
>                 "activationDate": "2019-09-01T15:01:46Z",
>                 "expirationDate": "2020-08-31T15:01:46Z"
>             }
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/move`

> Path added  
> 
> POST
> 
> _moveOrganizationLicenses_  
> **Move licenses to another organization. This will also move any devices that the licenses are assigned to**
> 
>     {
>         "destOrganizationId": "2930418",
>         "licenseIds": [
>             "123",
>             "456"
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/moveSeats`

> Path added  
> 
> POST
> 
> _moveOrganizationLicensesSeats_  
> **Move SM seats to another organization**
> 
>     {
>         "destOrganizationId": "2930418",
>         "licenseId": "1234",
>         "seatCount": 20
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/renewSeats`

> Path added  
> 
> POST
> 
> _renewOrganizationLicensesSeats_  
> **Renew SM seats of a license. This will extend the license expiration date of managed SM devices covered by this license**
> 
>     {
>         "resultingLicenses": [
>             {
>                 "id": "1234",
>                 "licenseType": "SME",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "deviceSerial": null,
>                 "networkId": "N_24329156",
>                 "state": "active",
>                 "seatCount": 25,
>                 "totalDurationInDays": 365,
>                 "durationInDays": 365,
>                 "permanentlyQueuedLicenses": [],
>                 "claimDate": "2019-08-29T12:40:10Z",
>                 "activationDate": "2019-09-01T15:01:46Z",
>                 "expirationDate": "2020-08-31T15:01:46Z"
>             }
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/licenses/{licenseId}`

> Path added  
> 
> GET
> 
> _getOrganizationLicense_  
> **Display a license**
> 
>     {
>         "id": "1234",
>         "licenseType": "MX64-ENT",
>         "licenseKey": "Z21234567890",
>         "orderNumber": "4C1234567",
>         "deviceSerial": "Q234-ABCD-5678",
>         "networkId": "N_24329156",
>         "state": "active",
>         "seatCount": null,
>         "totalDurationInDays": 425,
>         "durationInDays": 365,
>         "permanentlyQueuedLicenses": [
>             {
>                 "id": "5678",
>                 "licenseType": "MX64-ENT",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "durationInDays": 60
>             }
>         ],
>         "claimDate": "2019-08-29T12:40:10Z",
>         "activationDate": "2019-09-01T15:01:46Z",
>         "expirationDate": "2020-10-30T15:01:46Z"
>     }
> 
>   
> 
> PUT
> 
> _updateOrganizationLicense_  
> **Update a license**
> 
>     {
>         "id": "1234",
>         "licenseType": "MX64-ENT",
>         "licenseKey": "Z21234567890",
>         "orderNumber": "4C1234567",
>         "deviceSerial": "Q234-ABCD-5678",
>         "networkId": "N_24329156",
>         "state": "active",
>         "seatCount": null,
>         "totalDurationInDays": 425,
>         "durationInDays": 365,
>         "permanentlyQueuedLicenses": [
>             {
>                 "id": "5678",
>                 "licenseType": "MX64-ENT",
>                 "licenseKey": "Z21234567890",
>                 "orderNumber": "4C1234567",
>                 "durationInDays": 60
>             }
>         ],
>         "claimDate": "2019-08-29T12:40:10Z",
>         "activationDate": "2019-09-01T15:01:46Z",
>         "expirationDate": "2020-10-30T15:01:46Z"
>     }

* * *

Renamed
-------

#### PATH

`/organizations/{organizationId}/samlRoles/{id}`

> Path `/organizations/{organizationId}/samlRoles/{id}` renamed to `/organizations/{organizationId}/samlRoles/{samlRoleId}`

* * *
