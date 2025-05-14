---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnS2SInterface_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-vpns2sinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VpnS2SInterface
---

# Add-VpnS2SInterface

## SYNOPSIS
Create a S2S interface with the specified parameters.

## SYNTAX

### EncryptionType (Default)
```
Add-VpnS2SInterface [-Name] <String> [-Protocol <String>] [-Destination] <String[]> [-AdminStatus <Boolean>]
 [-PromoteAlternate <Boolean>] [-AuthenticationMethod <String>] [-PostConnectionIPv4Subnet <String[]>]
 [-PostConnectionIPv6Subnet <String[]>] [-InitiateConfigPayload <Boolean>] [-RadiusAttributeClass <String>]
 [-EnableQoS <EnableQoS>] [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>]
 [-IPv4TriggerFilter <String[]>] [-IPv6TriggerFilter <String[]>] [-Persistent] [-AutoConnectEnabled <Boolean>]
 [-IPv4TriggerFilterAction <Action>] [-IPv6TriggerFilterAction <Action>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-IPv4Subnet <String[]>] [-IPv6Subnet <String[]>]
 [-ResponderAuthenticationMethod <String>] [-PassThru] [[-RoutingDomain] <String>]
 [-Certificate <X509Certificate2>] [-SharedSecret <String>] [-NetworkOutageTimeSeconds <UInt32>]
 [-NumberOfTries <UInt32>] [-RetryIntervalSeconds <UInt32>] [-SALifeTimeSeconds <UInt32>]
 [-MMSALifeTimeSeconds <UInt32>] [-EapMethod <String>] [-InternalIPv4 <Boolean>] [-InternalIPv6 <Boolean>]
 [-IdleDisconnectSeconds <UInt32>] [-UserName <String>] [-Password <String>] [-SourceIpAddress <String>]
 [-LocalVpnTrafficSelector <CimInstance[]>] [-RemoteVpnTrafficSelector <CimInstance[]>]
 [-EncryptionType <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### GreInterface
```
Add-VpnS2SInterface [-Name] <String> [-Destination] <String[]> [-AdminStatus <Boolean>]
 [-EnableQoS <EnableQoS>] [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>] [-IPv4Subnet <String[]>]
 [-IPv6Subnet <String[]>] [-PassThru] [[-RoutingDomain] <String>] [-InternalIPv4 <Boolean>]
 [-InternalIPv6 <Boolean>] -SourceIpAddress <String> [[-GreKey] <UInt32>] [-GreTunnel] [-IPv4Address <String>]
 [-IPv6Address <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CustomPolicy
```
Add-VpnS2SInterface [-Name] <String> [-Protocol <String>] [-Destination] <String[]> [-AdminStatus <Boolean>]
 [-PromoteAlternate <Boolean>] [-AuthenticationMethod <String>] [-PostConnectionIPv4Subnet <String[]>]
 [-PostConnectionIPv6Subnet <String[]>] [-InitiateConfigPayload <Boolean>] [-RadiusAttributeClass <String>]
 [-EnableQoS <EnableQoS>] [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>]
 [-IPv4TriggerFilter <String[]>] [-IPv6TriggerFilter <String[]>] [-Persistent] [-AutoConnectEnabled <Boolean>]
 [-IPv4TriggerFilterAction <Action>] [-IPv6TriggerFilterAction <Action>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-IPv4Subnet <String[]>] [-IPv6Subnet <String[]>]
 [-ResponderAuthenticationMethod <String>] [-PassThru] [[-RoutingDomain] <String>]
 [-Certificate <X509Certificate2>] [-SharedSecret <String>] [-NetworkOutageTimeSeconds <UInt32>]
 [-NumberOfTries <UInt32>] [-RetryIntervalSeconds <UInt32>] [-SALifeTimeSeconds <UInt32>]
 [-MMSALifeTimeSeconds <UInt32>] [-EapMethod <String>] [-InternalIPv4 <Boolean>] [-InternalIPv6 <Boolean>]
 [-IdleDisconnectSeconds <UInt32>] [-UserName <String>] [-Password <String>] [-CustomPolicy]
 [-EncryptionMethod <EncryptionMethod>] [-IntegrityCheckMethod <IntegrityCheckMethod>]
 [-CipherTransformConstants <CipherTransformConstants>]
 [-AuthenticationTransformConstants <AuthenticationTransformConstants>] [-PfsGroup <PfsGroup>]
 [-DHGroup <DHGroup>] [-SourceIpAddress <String>] [-LocalVpnTrafficSelector <CimInstance[]>]
 [-RemoteVpnTrafficSelector <CimInstance[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VpnS2SInterface** cmdlet creates a site-to-site (S2S) interface with the specified parameters to customize Internet Protocol security (IPsec) settings.
If the *Protocol* parameter is set to AutomaticOnly the only authentication method allowed is username.
If the authentication method is a pre-shared key, only one interface can be enabled per destination and the initiator and responder policies are governed by what is specified per interface.
If the authentication method is username or machine certificates, only initiator policies are governed by what is specified per interface, responder policies are governed by what is specified on the server.
For incoming connections:

  -- If the authentication method is a pre-shared key, the interface whose destination IP matches the incoming IP is activated.

- If the authentication method is username, the interface whose name matches the username is activated.
- If the authentication method is certificates the interface whose name matches the certificate subject name is activated.

## EXAMPLES

### Example 1: Create a S2S VPN interface
```
PS C:\>Add-VpnS2SInterface -Name "EDGE1" 131.107.0.20 -Protocol IKEv2 -AuthenticationMethod PSKOnly -SharedSecret "ABC" -IPv4Subnet 10.2.0.0/24:100 -IPv6Subnet 2001:db8:2::/48:100
```

This command creates a site-to-site VPN interface by name EDGE1 to destination 131.107.0.20.
The protocol is IKEv2 and the authentication method is pre-shared key named ABC.
Traffic to 10.2.0.0/24 and subnet 2001:db8:2::/48 is sent over this interface if there is no other interface on the server that has same routes with metric less than 100 .
In case the interface is in disconnected state the connection is triggered if there is no other interface on the server that has same routes with metric less than 100.

### Example 2: Create an interface that uses EAP authentication
```
PS C:\>Add-VpnS2SInterface -IPv4Subnet @("131.0.1.0/24:254", "121.0.0.0/16:124") -UserName "abc@contoso.com" -Destination "30.0.0.1" -IPv6Subnet @("3ffe::/32:24", "2ffe::/32:24") -AuthenticationMethod "EAP" -Name "TestVpnS2SInterface" -RetryInterval 120 -EncryptionType "RequireEncryption" -InternalIPv4 1 -InternalIPv6 1 -NumberofTries 20 -AdminStatus $True -IdleDisconnectSeconds 300 -PromoteAlternate $True -Password "1111_aaaa" -PassThru
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet
----                 -----------          -----------  --------------- ----------
TestVpnS2SInterface  {30.0.0.1}           True         Disconnected    {131.0.1.0/24:254, 121.0.0.0/16:124}
```

This command creates an interface that uses EAP authentication method and multiple subnets are routed on this interface 131.0.1.0/24, 121.0.0.0/16.

### Example 3: Add an IKEv2 S2S VPN interface
```
PS C:\>Add-VpnS2SInterface -RoutingDomain Rd_001 -Name "Blue-Tunnel-2" -Protocol IKEv2 -Destination 100.0.0.7 -AuthenticationMethod PSKOnly -SharedSecret 111_aaa -Persistent -IPv4Subnet 172.23.90.4/32:100 -PassThru
RoutingDomain   Name                 Destination          AdminStatus  ConnectionState IPv4Subnet
-------------   ----                 -----------          -----------  --------------- ----------
Rd_001          Blue-Tunnel-2        {100.0.0.7}          True         Disconnected    {172.23.90.4/32:100}
```

This command adds an IKEv2 S2S VPN (Demand-Dial) interface to the Multi-Tenant Gateway for Routing Domain Rd_001

### Example 4: Add a Gre Tunnel interface
```
PS C:\>Add-VpnS2SInterface -GreTunnel -GreKey "1234" -RoutingDomain Rd_001 -Name "Blue-Tunnel-3" -Destination 100.0.0.8 -Persistent -IPv4Subnet 172.23.90.4/32:100 -PassThru
RoutingDomain   Name                 Destination          AdminStatus  ConnectionState IPv4Subnet
-------------   ----                 -----------          -----------  --------------- ----------
Rd_001          Blue-Tunnel-3        {100.0.0.8}          True         Connected    {172.23.90.4/32:100}
```

This command adds a Gre Tunnel interface to the Multi-Tenant Gateway for Routing Domain named Rd_001.

### Example 5: Add an IKEv2 S2S VPN interface with Traffic Selectors
```
PS C:\>Add-VpnS2SInterface -RoutingDomain Rd_001 -Name "Blue-Tunnel-2" -Protocol IKEv2 -Destination 100.0.0.7 -AuthenticationMethod PSKOnly -SharedSecret 111_aaa -Persistent -IPv4Subnet 172.23.90.4/32:100 -LocalVpnTrafficSelector $localTSObject -RemoteVpnTrafficSelector $RemoteTSObject -PassThru | fl *
IPv4TriggerFilterAction          :
IPv6TriggerFilterAction          :
Certificate                      :
EnableQoS                        : Enabled
AdminStatus                      : True
AuthenticationMethod             : PSKOnly
ConnectionState                  : Connected
Destination                      : {100.0.0.7}
EapMethod                        :
IdleDisconnect                   : 500
InitiateConfigPayload            : True
InterfaceType                    : FullRouter
InternalIPv4                     : True
InternalIPv6                     : True
IPv4Subnet                       : {172.23.90.4/32:100}
IPv4TriggerFilter                :
IPv6Subnet                       :
IPv6TriggerFilter                :
LastError                        : 0
LocalVpnTrafficSelector          : {VpnTrafficSelector}
MMSALifeTime                     : 28800
Name                             : Blue-Tunnel-2_9e8ddf33-cadc-48bd-861b-150311c53c9a
NetworkOutageTime                : 15
NumberOfTries                    : 3
Persistent                       : False
PostConnectionIPv4Subnet         :
PostConnectionIPv6Subnet         :
PromoteAlternate                 : False
Protocol                         : Ikev2
RemoteVpnTrafficSelector         : {VpnTrafficSelector}
ResponderAuthenticationMethod    : PSKOnly
RetryInterval                    : 60
RxBandwidthKbps                  : 0
SADataSizeForRenegotiation       : 33553408
SALifeTime                       : 3600
SourceIpAddress                  :
TxBandwidthKbps                  : 0
UnReachabilityReasons            :
UserName                         :
RoutingDomain                    : Rd_001_fa3a844e-c397-4004-9c48-547ce397fe59
PSComputerName                   :
```

This command adds an IKEv2 S2S VPN (Demand-Dial) interface to the Multi-Tenant Gateway for Routing Domain Rd_001.

## PARAMETERS

### -AdminStatus
Specifies the administrator status of the cmdlet.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationMethod
Specifies the AuthenticationMethod to be used by the S2S connection.
If a pre-shared key is specified as authentication method, there can only be one active site to site virtual private network (VPN) interface per destination IP address.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:
Accepted values: EAP, MachineCertificates, PSKOnly, MSCHAPv2,

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticationTransformConstants
Specifies the authentication transform plumbed in IPsec policy.

```yaml
Type: AuthenticationTransformConstants
Parameter Sets: CustomPolicy
Aliases: FirstTransformType, AuthenticationTransformConstant
Accepted values: MD596, SHA196, SHA256128, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoConnectEnabled
Specifies the activation of auto-reconnection.

```yaml
Type: Boolean
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Certificate
Specifies the certificate to be used in default store.
Applicable only if *AuthenticationMethod* is set to MachineCert.

```yaml
Type: X509Certificate2
Parameter Sets: EncryptionType, CustomPolicy
Aliases: Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CipherTransformConstants
Specifies the cipher plumbed in IPsec policy.

```yaml
Type: CipherTransformConstants
Parameter Sets: CustomPolicy
Aliases: OtherCipherAlgorithm, FirstCipherAlgorithm, CipherTransformConstant
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomPolicy
Specifies the custom IKE IPsec policy.

```yaml
Type: SwitchParameter
Parameter Sets: CustomPolicy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DHGroup
Specifies the Diffie-Hellman (DH) Group to use during IKE key exchanges.
Acceptable values for this parameter are:

- None
- Group1
- Group2
- Group14
- ECP256
- ECP384
- Group24

```yaml
Type: DHGroup
Parameter Sets: CustomPolicy
Aliases:
Accepted values: None, Group1, Group2, Group14, ECP256, ECP384, Group24

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Destination
Specifies the destination end-point of the S2S connection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RemoteTunnelEndpoint, RemoteTunnelHostname, RemoteAddress

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EapMethod
Specifies EAP method if *IkeLocalAuthenticationMethod* is EAP.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:
Accepted values: EAP-TLS, EAP-PEAP, EAP-MSCHAPv2,

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableQoS
Indicates whether to enable Quality of Service (QoS) on an interface.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: EnableQoS
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies the encryption method in the IKE policy.

```yaml
Type: EncryptionMethod
Parameter Sets: CustomPolicy
Aliases: Encryption
Accepted values: DES, DES3, AES128, AES192, AES256

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionType
Specifies the type of encryption.
The acceptable values for this parameter are:

- NoEncryption
- RequireEncryption
- OptionalEncryption
- MaximumEncryption

```yaml
Type: String
Parameter Sets: EncryptionType
Aliases:
Accepted values: NoEncryption, RequireEncryption, OptionalEncryption, MaximumEncryption

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GreKey
Specifies individual traffic flows within a Generic Routing Encapsulation (GRE) tunnel.

```yaml
Type: UInt32
Parameter Sets: GreInterface
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GreTunnel
Indicates whether this cmdlet uses the GRE tunnel capability for the Windows Server Gateway.

```yaml
Type: SwitchParameter
Parameter Sets: GreInterface
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Indicates whether the cmdlet sets custom IKE IPsec policies.

```yaml
Type: String
Parameter Sets: GreInterface
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Subnet
Specifies the IPv4 subnet that is routed on this connection with metric.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: IPv4TriggerSubnet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4TriggerFilter
Specifies a string array of IPv4 filters that trigger demand dial connections.

```yaml
Type: String[]
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IPv4TriggerFilterAction
Indicates whether a filter should trigger an S2S connection.

```yaml
Type: Action
Parameter Sets: EncryptionType, CustomPolicy
Aliases:
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IPv6Address
Indicates whether the cmdlet sets custom IKE IPsec policies.

```yaml
Type: String
Parameter Sets: GreInterface
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Subnet
Specifies the IPv6 subnet that is routed on this connection with metric.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: IPv6TriggerSubnet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6TriggerFilter
Specifies an array of IPv6 filters that trigger demand dial connections.

```yaml
Type: String[]
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IPv6TriggerFilterAction
Indicates whether a filter should trigger an S2S connection.

```yaml
Type: Action
Parameter Sets: EncryptionType, CustomPolicy
Aliases:
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IdleDisconnectSeconds
Specifies a value that specifies the time, in seconds, after which an idle connection is terminated.
Unless the idle time-out is disabled, the entire connection is terminated if the connection is idle for the specified interval.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: IdleDurationSeconds, IdleDisconnectSec

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiateConfigPayload
Indicates whether to initiate configuration payload negotiation.

```yaml
Type: Boolean
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IntegrityCheckMethod
Specifies the integrity method plumbed in IPsec policy.

```yaml
Type: IntegrityCheckMethod
Parameter Sets: CustomPolicy
Aliases: OtherHashAlgorithm, FirstIntegrityAlgorithm
Accepted values: MD5, SHA1, SHA256, SHA384

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalIPv4
Specifies Negotiation of IPv4 Address.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalIPv6
Specifies negotiation of IPv6 Address.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalVpnTrafficSelector
Specifies the initiator Traffic Selector object.

```yaml
Type: CimInstance[]
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MMSALifeTimeSeconds
Specifies the lifetime of main mode security association in seconds, after which the main mode security association is no longer valid.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: MMSaLifeTimeSec

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ElementName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkOutageTimeSeconds
Specifies the maximum network outage time after which the connection is disconnected.
Acceptable values for this parameter are:

- 6
- 9
- 12
- 15
- 30
- 60
- 120
- 240
- 360
- 720
- 900

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: NetworkOutageTimeSec
Accepted values: 3, 6, 9, 12, 15, 30, 60, 120, 240, 360, 720, 900

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberOfTries
Specifies the number of tries the connection is retried.
If you specify 0, the cmdlet will retry infinitely.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password of the username to be used for dialing the connection.
Applicable only if *AuthenticationMethod* is set to EAP.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistent
Indicates whether the connection state is persisted across the service restart or system reboots.

```yaml
Type: SwitchParameter
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfsGroup
Specifies the perfect forward secrecy (PFS) Group plumbed in IPsec policy.

```yaml
Type: PfsGroup
Parameter Sets: CustomPolicy
Aliases: PfsGroupId
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PostConnectionIPv4Subnet
Specifies the IPv4 subnet routes that are added to a site-to-site interface after the connection is established.
The values specified are not used to initiate the site-to-site VPN connection.

```yaml
Type: String[]
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PostConnectionIPv6Subnet
Specifies the IPv6 subnet routes that are added to a site-to-site interface after the connection is established.
The values specified are not used to initiate the site-to-site VPN connection.

```yaml
Type: String[]
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromoteAlternate
Specifies that an alternate IP address that connects successfully becomes the primary IP address, and the current primary IP address is moved to the alternate list.

```yaml
Type: Boolean
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Specifies the underlying protocol.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases: KeyModule
Accepted values: L2TP, IKEv2, Automatic, SSTP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusAttributeClass
Specifies a RADIUS attribute.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoteVpnTrafficSelector
Specifies the responder traffic selector object.

```yaml
Type: CimInstance[]
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResponderAuthenticationMethod
Specifies the responder AuthenticationMethod to be used by the S2S connection.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:
Accepted values: MachineCertificates, PSKOnly,

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetryIntervalSeconds
Number of seconds between retries.

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: RetryIntervalSec

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies an ID, as a string, for a routing domain.
The ID of a routing domain is a user-defined alphanumeric string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RxBandwidthKbps
Specifies the receive bandwidth limit, in kilobits per second (Kbps).

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SADataSizeForRenegotiationKilobytes
Specifies the number of kilobytes that are allowed to transfer using a security association (SA).
After that the SA will be renegotiated

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: SaRenegotiationDataSizeKB, LifeTimeKiloBytes

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeTimeSeconds
Lifetime of an SA in seconds, after which the SA is no longer valid

```yaml
Type: UInt32
Parameter Sets: EncryptionType, CustomPolicy
Aliases: SaLifeTimeSec, LifeTimeSeconds, QMSALifeTimeSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the text of the shared secret to be used in dialing the connection.
This is only applicable if *AuthenticationMethod* is set to PSK.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIpAddress
Specifies the source IPv4 or IPv6 addresses to use when dialing the connection.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: GreInterface
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.

The throttle limit applies only to the current command, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TxBandwidthKbps
Specifies a transmit bandwidth limit, in Kbps, for the interface.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies the username to be used for dialing this connection.
This is only applicable if the *AuthenticationMethod* parameter is set to EAP.

```yaml
Type: String
Parameter Sets: EncryptionType, CustomPolicy
Aliases: User

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Boolean

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.EnableQoS, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Nullable`1[[System.UInt64, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.Management.Automation.SwitchParameter

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.Action, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.EncryptionMethod

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.IntegrityCheckMethod

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.CipherTransformConstants

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.AuthenticationTransformConstants

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.PfsGroup

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.VpnS2SInterface.DHGroup

### Microsoft.Management.Infrastructure.CimInstance[]

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#VpnS2SInterface

## NOTES

## RELATED LINKS

[Connect-VpnS2SInterface](./Connect-VpnS2SInterface.md)

[Disconnect-VpnS2SInterface](./Disconnect-VpnS2SInterface.md)

[Get-VpnS2SInterface](./Get-VpnS2SInterface.md)

[Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)

[Set-VpnS2SInterface](./Set-VpnS2SInterface.md)

[Remote Access Cmdlets](./remoteaccess.md)

