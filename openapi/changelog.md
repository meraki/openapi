Meraki Dashboard API Changelog

Changelog
=========

Version 0.3.0 to 0.4.0

Renamed
-------

#### PATH

`` `/networks/{networkID}/switchStacks/{switchStackId}/remove` ``

> Path `` `/networks/{networkID}/switchStacks/{switchStackId}/remove` `` renamed to `/networks/{networkId}/switchStacks/{switchStackId}/remove`

* * *

Updates
-------

### Networks

**Update the site-to-site VPN settings of a network. Only valid for MX networks in NAT mode.**

#### PUT

`/networks/{networkId}/siteToSiteVpn`

> Property `mode` became required

> Param `updateNetworkSiteToSiteVpn` became required

* * *

### SSIDs

**Update the attributes of an SSID**

#### PUT

`/networks/{networkId}/ssids/{number}`

> Property `host` became required

> Property `secret` became required

* * *

### Radio settings

**Updates specified RF profile for this network**

#### PUT

`/networks/{networkId}/wireless/rfProfiles/{rfProfileId}`

> Property `minBitrate` type turn from `string` to `number`

> Property `minBitrate` type turn from `string` to `integer`

* * *

Changes
-------

### Networks

**Return a network**

#### GET

`/networks/{networkId}`

> Response property `productTypes` value added:
> 
>            
>             {
>               productTypes: ["appliance","switch","wireless"]
>             }
>     

* * *

**The traffic analysis data for this network.**

#### GET

`/networks/{networkId}/traffic`

> Optional param `t0` added

> Summary changed from `The traffic analysis data for this network. [Traffic Analysis with Hostname Visibility](https://documentation.meraki.com/MR/Monitoring_and_Reporting/Hostname_Visibility) must be enabled on the network.` to `The traffic analysis data for this network. [Traffic Analysis with Hostname Visibility](https://documentation.meraki.com/MR/Monitoring_and_Reporting/Hostname_Visibility) must be enabled on the network.`

* * *

**List the networks in an organization**

#### GET

`/organizations/{organizationId}/networks`

> Response property `productTypes` value added:
> 
>            
>             {
>               productTypes: ["appliance","switch","wireless"]
>             }
>     

* * *

### SSIDs

**Update the attributes of an SSID**

#### PUT

`/networks/{networkId}/ssids/{number}`

> Optional property `enterpriseAdminAccess` Added

> Optional property `radiusAttributeForGroupPolicies` Added

> Optional property `radiusOverride` Added

* * *

### Bluetooth clients

**List the Bluetooth clients seen by APs in this network**

#### GET

`/networks/{networkId}/bluetoothClients`

> Optional param `t0` added

> Response property `id` value added:
> 
>            
>             {
>               id: "1284392014819"
>             }
>     

> Response property `name` value added:
> 
>            
>             {
>               name: "Miles's phone"
>             }
>     

> Response property `deviceName` value added:
> 
>            
>             {
>               deviceName: "Bose QuietComfort 35"
>             }
>     

> Response property `manufacturer` value added:
> 
>            
>             {
>               manufacturer: "Bose"
>             }
>     

> Response property `lastSeen` value added:
> 
>            
>             {
>               lastSeen: 1526087474
>             }
>     

> Response property `seenByDeviceMac` value added:
> 
>            
>             {
>               seenByDeviceMac: "00:11:22:33:44:55"
>             }
>     

> Response property `inSightAlert` value added:
> 
>            
>             {
>               inSightAlert: false
>             }
>     

> Response property `outOfSightAlert` value added:
> 
>            
>             {
>               outOfSightAlert: false
>             }
>     

> Response property `tags` value added:
> 
>            
>             {
>               tags: ["tag1","tag2"]
>             }
>     

* * *

**Return a Bluetooth client. Bluetooth clients can be identified by their ID or their MAC.**

#### GET

`/networks/{networkId}/bluetoothClients/{bluetoothClientId}`

> Response property `id` value added:
> 
>            
>             {
>               id: "1284392014819"
>             }
>     

> Response property `name` value added:
> 
>            
>             {
>               name: "Miles's phone"
>             }
>     

> Response property `deviceName` value added:
> 
>            
>             {
>               deviceName: "Bose QuietComfort 35"
>             }
>     

> Response property `manufacturer` value added:
> 
>            
>             {
>               manufacturer: "Bose"
>             }
>     

> Response property `lastSeen` value added:
> 
>            
>             {
>               lastSeen: 1526087474
>             }
>     

> Response property `seenByDeviceMac` value added:
> 
>            
>             {
>               seenByDeviceMac: "00:11:22:33:44:55"
>             }
>     

> Response property `inSightAlert` value added:
> 
>            
>             {
>               inSightAlert: false
>             }
>     

> Response property `outOfSightAlert` value added:
> 
>            
>             {
>               outOfSightAlert: false
>             }
>     

> Response property `tags` value added:
> 
>            
>             {
>               tags: ["tag1","tag2"]
>             }
>     

* * *

### Clients

**Return the client associated with the given identifier. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.**

#### GET

`/networks/{networkId}/clients/{clientId}`

> Response property `status` value added:
> 
>            
>             {
>               status: "Online"
>             }
>     

* * *

### Management interface settings

**Return the management interface settings for a device**

#### GET

`/networks/{networkId}/devices/{serial}/managementInterfaceSettings`

> Response property `ddnsHostnames` value added:
> 
>            
>             {
>               ddnsHostnames: {"activeDdnsHostname":"mx1-sample.dynamic-m.com","ddnsHostnameWan1":"mx1-sample-1.dynamic-m.com","ddnsHostnameWan2":"mx1-sample-2.dynamic-m.com"}
>             }
>     

* * *

### Switch settings

#### PATH

`/networks/{networkId}/switch/settings/qosRules`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsQosRules_  
> **List quality of service rules**
> 
>     [
>         {
>             "id": "1284392014819",
>             "vlan": 100,
>             "protocol": "TCP",
>             "srcPort": 2000,
>             "srcPortRange": null,
>             "dstPort": null,
>             "dstPortRange": "3000-3100",
>             "dscp": 0
>         }
>     ]
> 
>   
> 
> POST
> 
> _createNetworkSwitchSettingsQosRule_  
> **Add a quality of service rule**
> 
>     {
>         "id": "1284392014819",
>         "vlan": 100,
>         "protocol": "TCP",
>         "srcPort": 2000,
>         "srcPortRange": null,
>         "dstPort": null,
>         "dstPortRange": "3000-3100",
>         "dscp": 0
>     }

* * *

#### PATH

`/networks/{networkId}/switch/settings/qosRules/order`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsQosRulesOrder_  
> **Return the quality of service rule IDs by order in which they will be processed by the switch**
> 
>     {
>         "ruleIds": [
>             "1284392014819",
>             "2983092129865"
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchSettingsQosRulesOrder_  
> **Update the order in which the rules should be processed by the switch**
> 
>     {
>         "ruleIds": [
>             "1284392014819",
>             "2983092129865"
>         ]
>     }

* * *

#### PATH

`/networks/{networkId}/switch/settings/qosRules/{qosRuleId}`

> Path added  
> 
> GET
> 
> _getNetworkSwitchSettingsQosRule_  
> **Return a quality of service rule**
> 
>     {
>         "id": "1284392014819",
>         "vlan": 100,
>         "protocol": "TCP",
>         "srcPort": 2000,
>         "srcPortRange": null,
>         "dstPort": null,
>         "dstPortRange": "3000-3100",
>         "dscp": 0
>     }
> 
>   
> 
> PUT
> 
> _updateNetworkSwitchSettingsQosRule_  
> **Update a quality of service rule**
> 
>     {
>         "id": "1284392014819",
>         "vlan": 100,
>         "protocol": "TCP",
>         "srcPort": 2000,
>         "srcPortRange": null,
>         "dstPort": null,
>         "dstPortRange": "3000-3100",
>         "dscp": 0
>     }
> 
>   
> 
> DELETE
> 
> _deleteNetworkSwitchSettingsQosRule_  
> **Delete a quality of service rule**

* * *

**Update switch network settings**

#### PUT

`/networks/{networkId}/switch/settings`

> Optional property `vlan` Added

* * *

**Returns the switch network settings**

#### GET

`/networks/{networkId}/switch/settings`

> Response property `vlan` value added:
> 
>            
>             {
>               vlan: 100
>             }
>     

* * *

### Uplink settings

**Updates the uplink settings for your MX network.**

#### PUT

`/networks/{networkId}/uplinkSettings`

> Property `limitUp` Deleted

> Property `limitDown` Deleted

> Optional property `wan1` Added

> Optional property `wan2` Added

> Optional property `cellular` Added

* * *

### Admins

**Update an administrator**

#### PUT

`/organizations/{organizationId}/admins/{id}`

> Property `email` Deleted

* * *

### Devices

**List the devices in an organization**

#### GET

`/organizations/{organizationId}/devices`

> Response property `firmware` value added:
> 
>            
>             {
>               firmware: "wireless-25-14"
>             }
>     

* * *

### Dashboard branding policies

#### PATH

`/organizations/{organizationId}/brandingPolicies`

> Path added  
> 
> GET
> 
> _getOrganizationBrandingPolicies_  
> **List the branding policies of an organization**
> 
>     [
>         {
>             "brandingPolicyId": "456",
>             "name": "My Branding Policy",
>             "enabled": true,
>             "adminSettings": {
>                 "appliesTo": "All admins of networks...",
>                 "values": [
>                     "N_1234",
>                     "L_5678"
>                 ]
>             },
>             "helpSettings": {
>                 "helpTab": "show",
>                 "getHelpSubtab": "default or inherit",
>                 "communitySubtab": "show",
>                 "casesSubtab": "hide",
>                 "dataProtectionRequestsSubtab": "default or inherit",
>                 "getHelpSubtabKnowledgeBaseSearch": "<h1>Some custom HTML content</h1>",
>                 "universalSearchKnowledgeBaseSearch": "hide",
>                 "ciscoMerakiProductDocumentation": "show",
>                 "supportContactInfo": "show",
>                 "newFeaturesSubtab": "show",
>                 "firewallInfoSubtab": "hide",
>                 "apiDocsSubtab": "default or inherit",
>                 "hardwareReplacementsSubtab": "hide",
>                 "smForums": "hide"
>             }
>         }
>     ]
> 
>   
> 
> POST
> 
> _createOrganizationBrandingPolicy_  
> **Add a new branding policy to an organization**
> 
>     {
>         "brandingPolicyId": "456",
>         "name": "My Branding Policy",
>         "enabled": true,
>         "adminSettings": {
>             "appliesTo": "All admins of networks...",
>             "values": [
>                 "N_1234",
>                 "L_5678"
>             ]
>         },
>         "helpSettings": {
>             "helpTab": "show",
>             "getHelpSubtab": "default or inherit",
>             "communitySubtab": "show",
>             "casesSubtab": "hide",
>             "dataProtectionRequestsSubtab": "default or inherit",
>             "getHelpSubtabKnowledgeBaseSearch": "<h1>Some custom HTML content</h1>",
>             "universalSearchKnowledgeBaseSearch": "hide",
>             "ciscoMerakiProductDocumentation": "show",
>             "supportContactInfo": "show",
>             "newFeaturesSubtab": "show",
>             "firewallInfoSubtab": "hide",
>             "apiDocsSubtab": "default or inherit",
>             "hardwareReplacementsSubtab": "hide",
>             "smForums": "hide"
>         }
>     }

* * *

#### PATH

`/organizations/{organizationId}/brandingPolicies/priorities`

> Path added  
> 
> GET
> 
> _getOrganizationBrandingPoliciesPriorities_  
> **Return the branding policy IDs of an organization in priority order. IDs are ordered in ascending order of priority (IDs later in the array have higher priority).**
> 
>     {
>         "brandingPolicyIds": [
>             "123",
>             "456",
>             "789"
>         ]
>     }
> 
>   
> 
> PUT
> 
> _updateOrganizationBrandingPoliciesPriorities_  
> **Update the priority ordering of an organization's branding policies.**
> 
>     {
>         "brandingPolicyIds": [
>             "123",
>             "456",
>             "789"
>         ]
>     }

* * *

#### PATH

`/organizations/{organizationId}/brandingPolicies/{brandingPolicyId}`

> Path added  
> 
> GET
> 
> _getOrganizationBrandingPolicy_  
> **Return a branding policy**
> 
>     {
>         "brandingPolicyId": "456",
>         "name": "My Branding Policy",
>         "enabled": true,
>         "adminSettings": {
>             "appliesTo": "All admins of networks...",
>             "values": [
>                 "N_1234",
>                 "L_5678"
>             ]
>         },
>         "helpSettings": {
>             "helpTab": "show",
>             "getHelpSubtab": "default or inherit",
>             "communitySubtab": "show",
>             "casesSubtab": "hide",
>             "dataProtectionRequestsSubtab": "default or inherit",
>             "getHelpSubtabKnowledgeBaseSearch": "<h1>Some custom HTML content</h1>",
>             "universalSearchKnowledgeBaseSearch": "hide",
>             "ciscoMerakiProductDocumentation": "show",
>             "supportContactInfo": "show",
>             "newFeaturesSubtab": "show",
>             "firewallInfoSubtab": "hide",
>             "apiDocsSubtab": "default or inherit",
>             "hardwareReplacementsSubtab": "hide",
>             "smForums": "hide"
>         }
>     }
> 
>   
> 
> PUT
> 
> _updateOrganizationBrandingPolicy_  
> **Update a branding policy**
> 
>     {
>         "brandingPolicyId": "456",
>         "name": "My Branding Policy",
>         "enabled": true,
>         "adminSettings": {
>             "appliesTo": "All admins of networks...",
>             "values": [
>                 "N_1234",
>                 "L_5678"
>             ]
>         },
>         "helpSettings": {
>             "helpTab": "show",
>             "getHelpSubtab": "default or inherit",
>             "communitySubtab": "show",
>             "casesSubtab": "hide",
>             "dataProtectionRequestsSubtab": "default or inherit",
>             "getHelpSubtabKnowledgeBaseSearch": "<h1>Some custom HTML content</h1>",
>             "universalSearchKnowledgeBaseSearch": "hide",
>             "ciscoMerakiProductDocumentation": "show",
>             "supportContactInfo": "show",
>             "newFeaturesSubtab": "show",
>             "firewallInfoSubtab": "hide",
>             "apiDocsSubtab": "default or inherit",
>             "hardwareReplacementsSubtab": "hide",
>             "smForums": "hide"
>         }
>     }
> 
>   
> 
> DELETE
> 
> _deleteOrganizationBrandingPolicy_  
> **Delete a branding policy**

* * *
