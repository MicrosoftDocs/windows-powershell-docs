---
author: andreabarr
Download Help Link: https://aka.ms/winsvr-2012-pshelp
Help Version: 3.0.0.0
Locale: en-US
manager: dansimp
Module Guid: d9d222a9-756c-41f8-b23a-2a596093216b
Module Name: RemoteAccess
ms.author: v-anbarr
ms.reviewer: 
---

# RemoteAccess Module
## Description
This reference provides cmdlet descriptions and syntax for all Remote Access-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## RemoteAccess Cmdlets
### [Add-DAAppServer](./Add-DAAppServer.md)
Adds a new application server security group to the DirectAccess (DA) deployment, adds an application servers to an application server security group that is already part of the DirectAccess deployment, and adds or updates application server Group Policy Object (GPO) in a domain.

### [Add-DAClient](./Add-DAClient.md)
Adds one or more client computer security groups (SGs) to the DirectAccess (DA) deployment, adds one or more DA client Group Policy Objects (GPOs) in one or more domains, adds one or more SGs of down-level clients to the DA deployment in a multi-site deployment, or adds one or more down-level DA client GPOs in one or more domains in a multi-site deployment.

### [Add-DAClientDnsConfiguration](./Add-DAClientDnsConfiguration.md)
Adds the specified DNS suffix, DNS server addresses, or proxy server set to the Name Resolution Policy Table (NRPT).

### [Add-DAEntryPoint](./Add-DAEntryPoint.md)
Adds an entry point to a multi-site deployment.

### [Add-DAMgmtServer](./Add-DAMgmtServer.md)
Adds the specified Management servers to the DirectAccess (DA) deployment.

### [Add-RemoteAccessLoadBalancerNode](./Add-RemoteAccessLoadBalancerNode.md)
Adds a server to the load balancing cluster.

### [Add-RemoteAccessRadius](./Add-RemoteAccessRadius.md)
Adds a new external RADIUS server for VPN authentication, accounting for DirectAccess (DA) and VPN, or one-time password (OTP) authentication for DA.

### [Add-VpnIPAddressRange](./Add-VpnIPAddressRange.md)
Adds a new IPv4 address range from which IPv4 addresses can be assigned to VPN clients.

### [Add-VpnS2SInterface](./Add-VpnS2SInterface.md)
Creates a site-to-site (S2S) interface with the specified parameters.

### [Clear-RemoteAccessInboxAccountingStore](./Clear-RemoteAccessInboxAccountingStore.md)
Clears the inbox accounting store for the specified time period.

### [Clear-VpnS2SInterfaceStatistics](./Clear-VpnS2SInterfaceStatistics.md)
Clears statistics for a site-to-site (S2S) interface.

### [Connect-VpnS2SInterface](./Connect-VpnS2SInterface.md)
Connects a site-to-site (S2S) interface that is currently not connected.

### [Disable-DAMultiSite](./Disable-DAMultiSite.md)
Disables a multi-site deployment that contains a single entry point.

### [Disable-DAOtpAuthentication](./Disable-DAOtpAuthentication.md)
Disables one-time password (OTP) authentication for DirectAccess (DA) users.

### [Disconnect-VpnS2SInterface](./Disconnect-VpnS2SInterface.md)
Disconnect a site-to-site (S2S) interface that is currently connected.

### [Disconnect-VpnUser](./Disconnect-VpnUser.md)
Disconnects a VPN connection originated by a specific user or originating from a specific client computer.

### [Enable-DAMultiSite](./Enable-DAMultiSite.md)
Enables and configures a multi-site deployment, and adds the first entry point.

### [Enable-DAOtpAuthentication](./Enable-DAOtpAuthentication.md)
Enables and configures one-time password (OTP) authentication for DirectAccess (DA) users.

### [Get-DAAppServer](./Get-DAAppServer.md)
Displays the list of application server security groups that are part of the DirectAccess (DA) deployment and the properties of the connections made to the application servers in the groups.

### [Get-DAClient](./Get-DAClient.md)
Displays the list of client security groups that are part of the DirectAccess (DA) deployment and the client properties.

### [Get-DAClientDnsConfiguration](./Get-DAClientDnsConfiguration.md)
Displays all the Name Resolution Policy Table (NRPT) entries and the local name resolution property.

### [Get-DAEntryPoint](./Get-DAEntryPoint.md)
Displays the settings for an entry point.

### [Get-DAEntryPointDC](./Get-DAEntryPointDC.md)
Retrieves a list of entry points and the associated domain controllers (DCs).

### [Get-DAMgmtServer](./Get-DAMgmtServer.md)
Displays the configured management servers.

### [Get-DAMultiSite](./Get-DAMultiSite.md)
Retrieves global settings applied to all entry points in a multi-site deployment.

### [Get-DANetworkLocationServer](./Get-DANetworkLocationServer.md)
Displays the detailed Network Location Server (NLS) configuration.

### [Get-DAOtpAuthentication](./Get-DAOtpAuthentication.md)
Displays one-time password (OTP) authentication settings for DirectAccess (DA).

### [Get-DAServer](./Get-DAServer.md)
Displays the properties of the DirectAccess (DA) server.

### [Get-RemoteAccess](./Get-RemoteAccess.md)
Displays the configuration of DirectAccess (DA) and VPN (both Remote Access VPN and site-to-site VPN).

### [Get-RemoteAccessAccounting](./Get-RemoteAccessAccounting.md)
Displays the accounting configuration for Remote Access, such as the different types of accounting that are enabled and the respective configuration.

### [Get-RemoteAccessConnectionStatistics](./Get-RemoteAccessConnectionStatistics.md)
Displays the statistics of real-time, currently active DirectAccess (DA) and VPN connections and the statistics of DA and VPN historical connections for a specified time duration.

### [Get-RemoteAccessConnectionStatisticsSummary](./Get-RemoteAccessConnectionStatisticsSummary.md)
Displays the summary statistics of real-time, currently active DirectAccess (DA) and VPN connections and the summary statistics of DA and VPN historical connections for a specified time duration.

### [Get-RemoteAccessHealth](./Get-RemoteAccessHealth.md)
Obtains the current health of a RemoteAccess (RA) deployment.

### [Get-RemoteAccessLoadBalancer](./Get-RemoteAccessLoadBalancer.md)
Displays load balanced cluster settings.

### [Get-RemoteAccessRadius](./Get-RemoteAccessRadius.md)
Displays the list of RADIUS servers including RADIUS for VPN authentication, RADIUS for DirectAccess (DA) and VPN Accounting, and RADIUS for one-time password (OTP) authentication for DA.

### [Get-RemoteAccessUserActivity](./Get-RemoteAccessUserActivity.md)
Displays the resources accessed over the active DirectAccess (DA) and VPN connections and the resources accessed over historical DA and VPN connections.

### [Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)
Retrieves authentication parameters configured on a VPN server.

### [Get-VpnS2SInterface](./Get-VpnS2SInterface.md)
Retrieves configuration details for a site-to-site (S2S) interface.

### [Get-VpnS2SInterfaceStatistics](./Get-VpnS2SInterfaceStatistics.md)
Retrieves statistics of a site-to-site (S2S) interface.

### [Get-VpnServerIPsecConfiguration](./Get-VpnServerIPsecConfiguration.md)
Gets IPsec parameters configured on the VPN server.

### [Install-RemoteAccess](./Install-RemoteAccess.md)
Performs prerequisite checks for DirectAccess (DA) to ensure that it can be installed, installs DA for remote access (RA) (includes management of remote clients) or for management of remote clients only, and installs VPN (both Remote Access VPN and site-to-site VPN).

### [Remove-DAAppServer](./Remove-DAAppServer.md)
Removes the specified list of application server security groups (SGs) from the DirectAccess (DA) deployment, removes the specified application servers from the specified DA application server SG,and removes the application server Group Policy Objects (GPOs) in the specified domains.

### [Remove-DAClient](./Remove-DAClient.md)
Removes one or more client computer security groups (SGs) from the DirectAccess (DA) deployment, removes one or more DA client Group Policy Objects (GPOs) from domains, removes one or more SGs of down-level clients (down-level clients can connect only to the specified site) from the DA deployment in a multi-site deployment, and removes one or more down-level DA client GPOs from domains in a multi-site deployment.

### [Remove-DAClientDnsConfiguration](./Remove-DAClientDnsConfiguration.md)
Removes the Name Resolution Policy Table (NRPT) entry corresponding to the specified DNS suffix from the NRPT.

### [Remove-DAEntryPoint](./Remove-DAEntryPoint.md)
Removes an entry point from a multi-site deployment.

### [Remove-DAMgmtServer](./Remove-DAMgmtServer.md)
Removes the specified management servers from the DirectAccess (DA) deployment.

### [Remove-RemoteAccessLoadBalancerNode](./Remove-RemoteAccessLoadBalancerNode.md)
Removes a server from the network load balancing (NLB) cluster.

### [Remove-RemoteAccessRadius](./Remove-RemoteAccessRadius.md)
Removes an external RADIUS server from being used for VPN authentication, accounting for both DirectAccess (DA) and VPN, or one-time password (OTP) authentication for DA.

### [Remove-VpnIPAddressRange](./Remove-VpnIPAddressRange.md)
Removes an existing IPv4 address range from the pool for IP address assignment.

### [Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)
Removes a specified site-to-site (S2S) interface.

### [Set-DAAppServerConnection](./Set-DAAppServerConnection.md)
Configures the properties of the connection to application servers and the IPsec security traffic protection policies for the connection.

### [Set-DAClient](./Set-DAClient.md)
Configures the properties related to a DirectAccess (DA) client.

### [Set-DAClientDnsConfiguration](./Set-DAClientDnsConfiguration.md)
Configures the DNS server and proxy server addresses of a Name Resolution Policy Table (NRPT) entry and configures the local name resolution property.

### [Set-DAEntryPoint](./Set-DAEntryPoint.md)
Configures settings for the entry point.

### [Set-DAEntryPointDC](./Set-DAEntryPointDC.md)
Modifies domain controller (DC) settings for the entry point.

### [Set-DAMultiSite](./Set-DAMultiSite.md)
Configures global settings for all entry points in a multi-site deployment.

### [Set-DANetworkLocationServer](./Set-DANetworkLocationServer.md)
Configures the Network Location Server (NLS).

### [Set-DAOtpAuthentication](./Set-DAOtpAuthentication.md)
Configures one-time password (OTP) authentication settings for DirectAccess (DA).

### [Set-DAServer](./Set-DAServer.md)
Sets the properties specific to the DirectAccess (DA) server.

### [Set-RemoteAccess](./Set-RemoteAccess.md)
Modifies the configuration that is common to both DirectAccess (DA) and VPN such SSL certificate, Internal interface, and Internet interface.

### [Set-RemoteAccessAccounting](./Set-RemoteAccessAccounting.md)
Sets the enabled state for inbox and RADIUS accounting for both external RADIUS and Windows accounting and configures the settings when enabled.

### [Set-RemoteAccessInboxAccountingStore](./Set-RemoteAccessInboxAccountingStore.md)
Modifies the size of the inbox accounting store.

### [Set-RemoteAccessLoadBalancer](./Set-RemoteAccessLoadBalancer.md)
Configures load balancing on the Remote Access (RA) server or the cluster server.

### [Set-RemoteAccessRadius](./Set-RemoteAccessRadius.md)
Edits the properties associated with an external RADIUS server being used for VPN authentication, accounting for DirectAccess (DA) and VPN, and one-time password (OTP) authentication for DA.

### [Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)
Sets the authentication method for incoming site-to-site (S2S) VPN interfaces on a Routing and Remote Access (RRAS) server.

### [Set-VpnAuthType](./Set-VpnAuthType.md)
Sets the authentication type to be used for connecting to a VPN.

### [Set-VpnIPAddressAssignment](./Set-VpnIPAddressAssignment.md)
Configures the IPv4 address assignment method or the IPv6 prefix for IPv6 address assignment.

### [Set-VpnS2SInterface](./Set-VpnS2SInterface.md)
Modifies parameters for a site-to-site (S2S) interface.

### [Set-VpnServerIPsecConfiguration](./Set-VpnServerIPsecConfiguration.md)
Sets the IPsec parameters for a site-to-site (S2S) server.

### [Uninstall-RemoteAccess](./Uninstall-RemoteAccess.md)
Uninstalls DirectAccess (DA) and VPN, both Remote Access (RA) VPN and site-to-site VPN.

### [Update-DAMgmtServer](./Update-DAMgmtServer.md)
Updates the list of Management servers of the DirectAccess (DA) deployment.

