Meraki Dashboard API Changelog

# Changelog

Version 0.4.0 to 0.5.0

## Changes

### Clients

**Return the splash authorization for a client, for each SSID they've associated with through splash. Only enabled SSIDs with Click-through splash enabled will be included. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.**

#### GET

`/networks/{networkId}/clients/{clientId}/splashAuthorizationStatus`

> Summary changed from `Return the splash authorization for a client, for each SSID they've associated with through splash. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.` to `Return the splash authorization for a client, for each SSID they've associated with through splash. Only enabled SSIDs with Click-through splash enabled will be included. Clients can be identified by a client key or either the MAC or IP depending on whether the network uses Track-by-IP.`

---

### Devices

**List the devices in a network**

#### GET

`/networks/{networkId}/devices`

> Response property `floorPlanId` value added:
>
>             {
>               floorPlanId: "g_1234567"
>             }

---

**Return a single device**

#### GET

`/networks/{networkId}/devices/{serial}`

> Response property `floorPlanId` value added:
>
>             {
>               floorPlanId: "g_1234567"
>             }

---

**Update the attributes of a device**

#### PUT

`/networks/{networkId}/devices/{serial}`

> Optional property `floorPlanId` Added

---

### SM

**List the devices enrolled in an SM network with various specified fields and filters**

#### GET

`/networks/{networkId}/sm/devices`

> Optional param `batchSize` added

---

#### PATH

`/networks/{networkId}/sm/device/{deviceId}/refreshDetails`

> Path added
>
> POST
>
> _refreshNetworkSmDeviceDetails_  
> **Refresh the details of a device**

---

### MX static routes

**List the static routes for an MX or teleworker network**

#### GET

`/networks/{networkId}/staticRoutes`

> Summary changed from `List the static routes for this network` to `List the static routes for an MX or teleworker network`

---

**Return a static route for an MX or teleworker network**

#### GET

`/networks/{networkId}/staticRoutes/{srId}`

> Summary changed from `Return a static route` to `Return a static route for an MX or teleworker network`

---

**Update a static route for an MX or teleworker network**

#### PUT

`/networks/{networkId}/staticRoutes/{srId}`

> Summary changed from `Update a static route` to `Update a static route for an MX or teleworker network`

---

**Add a static route for an MX or teleworker network**

#### POST

`/networks/{networkId}/staticRoutes`

> Summary changed from `Add a static route` to `Add a static route for an MX or teleworker network`

---

**Delete a static route from an MX or teleworker network**

#### DELETE

`/networks/{networkId}/staticRoutes/{srId}`

> Summary changed from `Delete a static route from a network` to `Delete a static route from an MX or teleworker network`

---

### Organizations

**List the organizations that the user has privileges on**

#### GET

`/organizations`

> Response property `url` value added:
>
>             {
>               url: "https://dashboard.meraki.com/o/VjjsAd/manage/organization/overview"
>             }

---

**Return an organization**

#### GET

`/organizations/{organizationId}`

> Response property `url` value added:
>
>             {
>               url: "https://dashboard.meraki.com/o/VjjsAd/manage/organization/overview"
>             }

---

### Connectivity monitoring destinations

#### PATH

`/networks/{networkId}/connectivityMonitoringDestinations`

> Path added
>
> GET
>
> _getNetworkConnectivityMonitoringDestinations_  
> **Return the connectivity testing destinations for an MX network**
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
> PUT
>
> _updateNetworkConnectivityMonitoringDestinations_  
> **Update the connectivity testing destinations for an MX network**
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

---

### Events

#### PATH

`/networks/{networkId}/events`

> Path added
>
> GET
>
> _getNetworkEvents_  
> **List the events for the network**
>
>     {
>         "message": null,
>         "pageStartAt": "2018-02-11T00:00:00.090210Z",
>         "pageEndAt": "2018-02-11T00:00:00.090210Z",
>         "events": [
>             {
>                 "occurredAt": "2018-02-11T00:00:00.090210Z",
>                 "networkId": "N_24329156",
>                 "type": "association",
>                 "description": "802.11 association",
>                 "clientId": "k74272e",
>                 "clientDescription": "Miles's phone",
>                 "deviceSerial": "Q234-ABCD-5678",
>                 "deviceName": "My AP",
>                 "ssidNumber": 1,
>                 "ssidName": "My SSID",
>                 "eventData": {
>                     "radio": "1",
>                     "vap": "1",
>                     "client_mac": "22:33:44:55:66:77",
>                     "client_ip": "1.2.3.4",
>                     "channel": "36",
>                     "rssi": "12",
>                     "aid": "2104009183"
>                 }
>             }
>         ]
>     }

---

#### PATH

`/networks/{networkId}/events/eventTypes`

> Path added
>
> GET
>
> _getNetworkEventsEventTypes_  
> **List the event type to human-readable description**
>
>     [
>         {
>             "category": "802.11",
>             "type": "association",
>             "description": "802.11 association"
>         }
>     ]

---

### Floorplans

#### PATH

`/networks/{networkId}/floorPlans`

> Path added
>
> GET
>
> _getNetworkFloorPlans_  
> **List the floor plans that belong to your network**
>
>     [
>         {
>             "floorPlanId": "g_1234567",
>             "imageUrl": "https://meraki-na.s3.amazonaws.com/assets/...",
>             "imageUrlExpiresAt": "2019-06-11 16:04:54 +00:00",
>             "imageExtension": "png",
>             "imageMd5": "2a9edd3f4ffd80130c647d13eacb59f3",
>             "name": "HQ Floor Plan",
>             "devices": [
>                 {
>                     "name": "My AP",
>                     "lat": 37.4180951010362,
>                     "lng": -122.098531723022,
>                     "serial": "Q234-ABCD-5678",
>                     "mac": "00:11:22:33:44:55",
>                     "model": "MR34",
>                     "address": "1600 Pennsylvania Ave",
>                     "notes": "My AP's note",
>                     "lanIp": "1.2.3.4",
>                     "tags": " recently-added ",
>                     "networkId": "N_24329156",
>                     "beaconIdParams": {
>                         "uuid": "00000000-0000-0000-0000-000000000000",
>                         "major": 5,
>                         "minor": 3
>                     },
>                     "firmware": "wireless-25-14",
>                     "floorPlanId": "g_1234567"
>                 }
>             ],
>             "width": 100,
>             "height": 150,
>             "center": {
>                 "lat": 37.770040510499996,
>                 "lng": -122.38714009525
>             },
>             "bottomLeftCorner": {
>                 "lat": 37.7696461495,
>                 "lng": -122.3880815506
>             },
>             "bottomRightCorner": {
>                 "lat": 37.771524649766654,
>                 "lng": -122.38795275055205
>             },
>             "topLeftCorner": {
>                 "lat": 37.769700101836364,
>                 "lng": -122.3888684251381
>             },
>             "topRightCorner": {
>                 "lat": 37.77157860210302,
>                 "lng": -122.38873962509012
>             }
>         }
>     ]
>
> POST
>
> _createNetworkFloorPlan_  
> **Upload a floor plan**
>
>     {
>         "floorPlanId": "g_1234567",
>         "imageUrl": "https://meraki-na.s3.amazonaws.com/assets/...",
>         "imageUrlExpiresAt": "2019-06-11 16:04:54 +00:00",
>         "imageExtension": "png",
>         "imageMd5": "2a9edd3f4ffd80130c647d13eacb59f3",
>         "name": "HQ Floor Plan",
>         "devices": [
>             {
>                 "name": "My AP",
>                 "lat": 37.4180951010362,
>                 "lng": -122.098531723022,
>                 "serial": "Q234-ABCD-5678",
>                 "mac": "00:11:22:33:44:55",
>                 "model": "MR34",
>                 "address": "1600 Pennsylvania Ave",
>                 "notes": "My AP's note",
>                 "lanIp": "1.2.3.4",
>                 "tags": " recently-added ",
>                 "networkId": "N_24329156",
>                 "beaconIdParams": {
>                     "uuid": "00000000-0000-0000-0000-000000000000",
>                     "major": 5,
>                     "minor": 3
>                 },
>                 "firmware": "wireless-25-14",
>                 "floorPlanId": "g_1234567"
>             }
>         ],
>         "width": 100,
>         "height": 150,
>         "center": {
>             "lat": 37.770040510499996,
>             "lng": -122.38714009525
>         },
>         "bottomLeftCorner": {
>             "lat": 37.7696461495,
>             "lng": -122.3880815506
>         },
>         "bottomRightCorner": {
>             "lat": 37.771524649766654,
>             "lng": -122.38795275055205
>         },
>         "topLeftCorner": {
>             "lat": 37.769700101836364,
>             "lng": -122.3888684251381
>         },
>         "topRightCorner": {
>             "lat": 37.77157860210302,
>             "lng": -122.38873962509012
>         }
>     }

---

#### PATH

`/networks/{networkId}/floorPlans/{floorPlanId}`

> Path added
>
> GET
>
> _getNetworkFloorPlan_  
> **Find a floor plan by ID**
>
>     {
>         "floorPlanId": "g_1234567",
>         "imageUrl": "https://meraki-na.s3.amazonaws.com/assets/...",
>         "imageUrlExpiresAt": "2019-06-11 16:04:54 +00:00",
>         "imageExtension": "png",
>         "imageMd5": "2a9edd3f4ffd80130c647d13eacb59f3",
>         "name": "HQ Floor Plan",
>         "devices": [
>             {
>                 "name": "My AP",
>                 "lat": 37.4180951010362,
>                 "lng": -122.098531723022,
>                 "serial": "Q234-ABCD-5678",
>                 "mac": "00:11:22:33:44:55",
>                 "model": "MR34",
>                 "address": "1600 Pennsylvania Ave",
>                 "notes": "My AP's note",
>                 "lanIp": "1.2.3.4",
>                 "tags": " recently-added ",
>                 "networkId": "N_24329156",
>                 "beaconIdParams": {
>                     "uuid": "00000000-0000-0000-0000-000000000000",
>                     "major": 5,
>                     "minor": 3
>                 },
>                 "firmware": "wireless-25-14",
>                 "floorPlanId": "g_1234567"
>             }
>         ],
>         "width": 100,
>         "height": 150,
>         "center": {
>             "lat": 37.770040510499996,
>             "lng": -122.38714009525
>         },
>         "bottomLeftCorner": {
>             "lat": 37.7696461495,
>             "lng": -122.3880815506
>         },
>         "bottomRightCorner": {
>             "lat": 37.771524649766654,
>             "lng": -122.38795275055205
>         },
>         "topLeftCorner": {
>             "lat": 37.769700101836364,
>             "lng": -122.3888684251381
>         },
>         "topRightCorner": {
>             "lat": 37.77157860210302,
>             "lng": -122.38873962509012
>         }
>     }
>
> PUT
>
> _updateNetworkFloorPlan_  
> **Update a floor plan's geolocation and other meta data**
>
>     {
>         "floorPlanId": "g_1234567",
>         "imageUrl": "https://meraki-na.s3.amazonaws.com/assets/...",
>         "imageUrlExpiresAt": "2019-06-11 16:04:54 +00:00",
>         "imageExtension": "png",
>         "imageMd5": "2a9edd3f4ffd80130c647d13eacb59f3",
>         "name": "HQ Floor Plan",
>         "devices": [
>             {
>                 "name": "My AP",
>                 "lat": 37.4180951010362,
>                 "lng": -122.098531723022,
>                 "serial": "Q234-ABCD-5678",
>                 "mac": "00:11:22:33:44:55",
>                 "model": "MR34",
>                 "address": "1600 Pennsylvania Ave",
>                 "notes": "My AP's note",
>                 "lanIp": "1.2.3.4",
>                 "tags": " recently-added ",
>                 "networkId": "N_24329156",
>                 "beaconIdParams": {
>                     "uuid": "00000000-0000-0000-0000-000000000000",
>                     "major": 5,
>                     "minor": 3
>                 },
>                 "firmware": "wireless-25-14",
>                 "floorPlanId": "g_1234567"
>             }
>         ],
>         "width": 100,
>         "height": 150,
>         "center": {
>             "lat": 37.770040510499996,
>             "lng": -122.38714009525
>         },
>         "bottomLeftCorner": {
>             "lat": 37.7696461495,
>             "lng": -122.3880815506
>         },
>         "bottomRightCorner": {
>             "lat": 37.771524649766654,
>             "lng": -122.38795275055205
>         },
>         "topLeftCorner": {
>             "lat": 37.769700101836364,
>             "lng": -122.3888684251381
>         },
>         "topRightCorner": {
>             "lat": 37.77157860210302,
>             "lng": -122.38873962509012
>         }
>     }
>
> DELETE
>
> _deleteNetworkFloorPlan_  
> **Destroy a floor plan**

---

### Switch settings

#### PATH

`/networks/{networkId}/switch/settings/mtu`

> Path added
>
> GET
>
> _getNetworkSwitchSettingsMtu_  
> **Return the MTU configuration**
>
>     {
>         "defaultMtuSize": 9578,
>         "overrides": [
>             {
>                 "switches": [
>                     "Q234-ABCD-0001",
>                     "Q234-ABCD-0002",
>                     "Q234-ABCD-0003"
>                 ],
>                 "mtuSize": 1500
>             },
>             {
>                 "switchProfiles": [
>                     "1284392014819",
>                     "2983092129865"
>                 ],
>                 "mtuSize": 1600
>             }
>         ]
>     }
>
> PUT
>
> _updateNetworkSwitchSettingsMtu_  
> **Update the MTU configuration**
>
>     {
>         "defaultMtuSize": 9578,
>         "overrides": [
>             {
>                 "switches": [
>                     "Q234-ABCD-0001",
>                     "Q234-ABCD-0002",
>                     "Q234-ABCD-0003"
>                 ],
>                 "mtuSize": 1500
>             },
>             {
>                 "switchProfiles": [
>                     "1284392014819",
>                     "2983092129865"
>                 ],
>                 "mtuSize": 1600
>             }
>         ]
>     }

---

#### PATH

`/networks/{networkId}/switch/settings/stormControl`

> Path added
>
> GET
>
> _getNetworkSwitchSettingsStormControl_  
> **Return the global enhanced storm control configuration**
>
>     {
>         "broadcastThreshold": 30,
>         "multicastThreshold": 30,
>         "unknownUnicastThreshold": 30
>     }
>
> PUT
>
> _updateNetworkSwitchSettingsStormControl_  
> **Update the global enhanced storm control configuration**
>
>     {
>         "broadcastThreshold": 30,
>         "multicastThreshold": 30,
>         "unknownUnicastThreshold": 30
>     }

---

#### PATH

`/networks/{networkId}/switch/settings/stp`

> Path added
>
> GET
>
> _getNetworkSwitchSettingsStp_  
> **Returns STP settings**
>
>     {
>         "rstpEnabled": true,
>         "stpBridgePriority": [
>             {
>                 "switches": [
>                     "Q234-ABCD-0001",
>                     "Q234-ABCD-0002",
>                     "Q234-ABCD-0003"
>                 ],
>                 "stpPriority": 4096
>             },
>             {
>                 "stacks": [
>                     "789102",
>                     "123456",
>                     "129102"
>                 ],
>                 "stpPriority": 28672
>             }
>         ]
>     }
>
> PUT
>
> _updateNetworkSwitchSettingsStp_  
> **Updates STP settings**
>
>     {
>         "rstpEnabled": true,
>         "stpBridgePriority": [
>             {
>                 "switches": [
>                     "Q234-ABCD-0001",
>                     "Q234-ABCD-0002",
>                     "Q234-ABCD-0003"
>                 ],
>                 "stpPriority": 4096
>             },
>             {
>                 "stacks": [
>                     "789102",
>                     "123456",
>                     "129102"
>                 ],
>                 "stpPriority": 28672
>             }
>         ]
>     }

---

### Wireless settings

#### PATH

`/networks/{networkId}/wireless/settings`

> Path added
>
> GET
>
> _getNetworkWirelessSettings_  
> **Return the wireless settings for a network**
>
>     {
>         "meshingEnabled": true,
>         "ipv6BridgeEnabled": false,
>         "locationAnalyticsEnabled": false
>     }
>
> PUT
>
> _updateNetworkWirelessSettings_  
> **Update the wireless settings for a network**
>
>     {
>         "meshingEnabled": true,
>         "ipv6BridgeEnabled": false,
>         "locationAnalyticsEnabled": false
>     }

---
