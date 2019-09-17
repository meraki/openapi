## Version 0.2.0 to 0.3.0
---
### What's New
---
* `GET` /networks/{networkId}/appliancePorts List per-port VLAN settings for all ports of a MX.
* `GET` /networks/{networkId}/appliancePorts/{appliancePortId} Return per-port VLAN settings for a single MX port.
* `PUT` /networks/{networkId}/appliancePorts/{appliancePortId} Update the per-port VLAN settings for a single MX port.
* `GET` /networks/{networkId}/devices/{serial}/wireless/status Return the SSID statuses of an access point
* `GET` /networks/{networkId}/merakiAuthUsers/{merakiAuthUserId} Return the Meraki Auth splash or RADIUS user
* `POST` /networks/{networkId}/swapWarmSpare Swap MX primary and warm spare appliances
* `PUT` /networks/{networkId}/switch/portSchedules/{portScheduleId} Update a switch port schedule
* `DELETE` /networks/{networkId}/switch/portSchedules/{portScheduleId} Delete a switch port schedule
* `GET` /networks/{networkId}/warmSpareSettings Return MX warm spare settings
* `PUT` /networks/{networkId}/warmSpareSettings Update MX warm spare settings
* `GET` /networks/{networkId}/wireless/rfProfiles/{rfProfileId} Return a RF profile
* `PUT` /networks/{networkId}/wireless/rfProfiles/{rfProfileId} Updates specified RF profile for this network
* `DELETE` /networks/{networkId}/wireless/rfProfiles/{rfProfileId} Delete a RF Profile
* `DELETE` /organizations/{organizationId}/configTemplates/{configTemplateId} Remove a configuration template
* `POST` /networks/{networkId}/switch/portSchedules Add a switch port schedule
* `POST` /networks/{networkId}/wireless/rfProfiles Creates new RF profile for this network

### What's Deprecated
---
* `GET` /networks/{networkId}/merakiAuthUsers/{id} Return the Meraki Auth splash or RADIUS user
* `DELETE` /organizations/{organizationId}/configTemplates/{id} Remove a configuration template

### What's Changed
---
`GET` /devices/{serial}/camera/analytics/overview Returns an overview of aggregate analytics data for a timespan  
    Parameters

        Add objectType //[optional] The object type for which analytics will be retrieved. The default object type is person. The available types are [person, vehicle].
`GET` /devices/{serial}/camera/analytics/recent Returns most recent record for analytics zones  
    Parameters

        Add objectType //[optional] The object type for which analytics will be retrieved. The default object type is person. The available types are [person, vehicle].
`GET` /devices/{serial}/camera/analytics/zones/{zoneId}/history Return historical records for analytic zones  
    Parameters

        Add objectType //[optional] The object type for which analytics will be retrieved. The default object type is person. The available types are [person, vehicle].
`PUT` /devices/{serial}/switchPorts/{number} Update a switch port  
    Parameters

        Add updateDeviceSwitchPort
`GET` /networks/{networkId}/bluetoothClients List the Bluetooth clients seen by APs in this network  
    Parameters

        Add timespan //The timespan, in seconds, used to look back from now for bluetooth clients
        Add includeConnectivityHistory //Include the connectivity history for this client
`GET` /networks/{networkId}/bluetoothClients/{bluetoothClientId} Return a Bluetooth client. Bluetooth clients can be identified by their ID or their MAC.  
    Parameters

        Add includeConnectivityHistory //Include the connectivity history for this client
        Add connectivityHistoryTimespan //The timespan, in seconds, for the connectivityHistory data. By default 1 day, 86400, will be used.
`PUT` /networks/{networkId}/firewalledServices/{service} Updates the accessibility settings for the given service ('ICMP', 'web', or 'SNMP')  
    Parameters

        Add updateNetworkFirewalledService
        updateNetworkFirewalledService change into required
`PUT` /networks/{networkId}/ssids/{number} Update the attributes of an SSID  
    Parameters

        Add updateNetworkSsid
`POST` /organizations/{organizationId}/actionBatches Create an action batch  
    Parameters

        Add createOrganizationActionBatch
`PUT` /organizations/{organizationId}/actionBatches/{actionBatchId} Update an action batch  
    Parameters

        Add updateOrganizationActionBatch
`POST` /organizations/{organizationId}/claim Claim a list of devices, licenses, and/or orders into an organization. When claiming by order, all devices and licenses in the order will be claimed; licenses will be added to the organization and devices will be placed in the organization's inventory.  
    Parameters

        Add claimOrganization

