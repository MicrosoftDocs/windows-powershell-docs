---
external help file: PS_VpnS2SInterface_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-vpns2sinterface?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VpnS2SInterface
---

# Add-VpnS2SInterface

## SYNOPSIS
Creates a site-to-site (S2S) interface with the specified parameters.

## SYNTAX

### EncryptionType (Default)
```
Add-VpnS2SInterface [-Name] <String> [-Protocol <String>] [-Destination] <String[]> [-AdminStatus <Boolean>]
 [-PromoteAlternate <Boolean>] [-AuthenticationMethod <String>] [-PostConnectionIPv4Subnet <String[]>]
 [-PostConnectionIPv6Subnet <String[]>] [-InitiateConfigPayload <Boolean>] [-RadiusAttributeClass <String>]
 [-EnableQoS <EnableQoS>] [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>]
 [-IPv4TriggerFilter <String[]>] [-IPv6TriggerFilter <String[]>] [-Persistent]
 [-IPv4TriggerFilterAction <Action>] [-IPv6TriggerFilterAction <Action>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-IPv4Subnet <String[]>] [-IPv6Subnet <String[]>]
 [-ResponderAuthenticationMethod <String>] [-PassThru] [[-RoutingDomain] <String>]
 [-Certificate <X509Certificate2>] [-SharedSecret <String>] [-NetworkOutageTimeSeconds <UInt32>]
 [-NumberOfTries <UInt32>] [-RetryIntervalSeconds <UInt32>] [-SALifeTimeSeconds <UInt32>] [-EapMethod <String>]
 [-InternalIPv4 <Boolean>] [-InternalIPv6 <Boolean>] [-IdleDisconnectSeconds <UInt32>] [-UserName <String>]
 [-Password <String>] [-SourceIpAddress <String>] [-EncryptionType <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomPolicy
```
Add-VpnS2SInterface [-Name] <String> [-Protocol <String>] [-Destination] <String[]> [-AdminStatus <Boolean>]
 [-PromoteAlternate <Boolean>] [-AuthenticationMethod <String>] [-PostConnectionIPv4Subnet <String[]>]
 [-PostConnectionIPv6Subnet <String[]>] [-InitiateConfigPayload <Boolean>] [-RadiusAttributeClass <String>]
 [-EnableQoS <EnableQoS>] [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>]
 [-IPv4TriggerFilter <String[]>] [-IPv6TriggerFilter <String[]>] [-Persistent]
 [-IPv4TriggerFilterAction <Action>] [-IPv6TriggerFilterAction <Action>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-IPv4Subnet <String[]>] [-IPv6Subnet <String[]>]
 [-ResponderAuthenticationMethod <String>] [-PassThru] [[-RoutingDomain] <String>]
 [-Certificate <X509Certificate2>] [-SharedSecret <String>] [-NetworkOutageTimeSeconds <UInt32>]
 [-NumberOfTries <UInt32>] [-RetryIntervalSeconds <UInt32>] [-SALifeTimeSeconds <UInt32>] [-EapMethod <String>]
 [-InternalIPv4 <Boolean>] [-InternalIPv6 <Boolean>] [-IdleDisconnectSeconds <UInt32>] [-UserName <String>]
 [-Password <String>] [-CustomPolicy] [-EncryptionMethod <EncryptionMethod>]
 [-IntegrityCheckMethod <IntegrityCheckMethod>] [-CipherTransformConstants <CipherTransformConstants>]
 [-AuthenticationTransformConstants <AuthenticationTransformConstants>] [-PfsGroup <PfsGroup>]
 [-DHGroup <DHGroup>] [-SourceIpAddress <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VpnS2SInterface** cmdlet creates a site-to-site (S2S) interface with the specified parameters.
Use the **CustomPolicy** parameter to customize IPsec settings.
If the **Protocol** parameter is set to Automatic, then the only authentication method allowed is user name.
If the **AuthenticationMethod** parameter is set to pre-shared key (PSK), then only one interface can be enabled per destination and the initiator and responder policies are governed by what is specified per interface.
If the **AuthenticationMethod** parameter is set to user name or computer certificates (MachineCert), then only initiator policies are governed by what is specified per interface and responder policies are governed by what is specified on the server.

For incoming connections: 
 
                      
 -- If the **AuthenticationMethod** parameter is set to PSK, the interface for which the destination IP matches the incoming IP is activated. 
 
                      
 -- If the **AuthenticationMethod** parameter is set to user name, then the name of the interface that matches the user name is activated. 
 
                      
 -- If the **AuthenticationMethod** parameter is set to certificates, then the name of the interface that matches the certificate subject name is activated.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-VpnS2SInterface -Nameedge1 -Destination 131.107.0.20 -Protocol IKEv2 -AuthenticationMethod PSKOnly -SharedSecret abc -IPv4Subnet 10.2.0.0/24:100 -IPv6Subnet 2001:db8:2::/48:100
```

This example creates a S2S VPN interface named edge1 to the destination server 131.107.0.20.
The protocol is IKEv2 and the authentication method is PSK.
The string abc is used as PSK.
Traffic to 10.2.0.0/24 and 2001:db8:2::/48 is sent over this interface if there is no other interface on the server that has same routes with a metric less than 100 .
In case the interface is in disconnected state the connection is triggered if there is no other interface on the server that has same routes with a metric less than 100.

### EXAMPLE 2
```
PS C:\>Add-VpnS2SInterface -IPv4Subnet @("131.0.1.0/24:254", "121.0.0.0/16:124") -UserName "abc@contoso.com" -Destination "30.0.0.1" -IPv6Subnet @("3ffe::/32:24", "2ffe::/32:24") -AuthenticationMethod "EAP" -Name "TestVpnS2SInterface" -RetryInterval 120 -EncryptionType "RequireEncryption" -InternalIPv4 1 -InternalIPv6 1 -NumberofTries 20 -AdminStatus $true -IdleDisconnectSeconds 300 -PromoteAlternate $true -Password "1111_aaaa" -PassThru
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet 
----                 -----------          -----------  --------------- ---------- 
TestVpnS2SInterface  {30.0.0.1}           True         Disconnected    {131.0.1.0/24:254, 121.0.0.0/16:124}
```

This example creates an interface that uses EAP authentication method and multiple subnets are routed on this interface including 131.0.1.0/24 and 121.0.0.0/16.

### EXAMPLE 3
```
PS C:\>Add-VpnS2SInterface -CustomPolicy -UserName "abc@contoso.com" -EncryptionMethod "AES128" -Destination "30.0.0.1" -Password "1111_aaaa" -DhGroup "Group2" -PfsGroup "PFS2" -CipherTransformConstants "AES128" -Name "TestVpnS2SInterface" -IntegrityCheckMethod "SHA256" -AuthenticationTransformConstants "SHA256128" -Protocol "IKEv2"
```

This example creates a S2S VPN interface using custom encryption settings.

### EXAMPLE 4
```
PS C:\>$cert1 = Get-ChildItem -Path cert:LocalMachine\My | Where-Object -FilterScript { $_.Subject -Like "*CN=edge1.contoso.com*" }



PS C:\>Add-VpnS2SInterface -Name e1 -Destination 1.1.1.1 -AuthenticationMethod MachineCertificates -Certificate $cert1 -ResponderAuthenticationMethod MachineCertificates -Protocol IKEv2
```

This example creates a S2S interface with authentication method of computer certificate and specifies the certificate for which the subject name is edge1.contoso.com.

## PARAMETERS

### -AdminStatus
Specifies the administrator status of the cmdlet.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Specifies the authentication method to be used by the S2S connection. 
 
                        
If PSK is specified, then there can only be one active S2S VPN interface per destination IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: EAP, MachineCertificates, PSKOnly, 

Required: False
Position: Named
Default value: EAP
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticationTransformConstants
Specifies a transform constant.
The acceptable values for this parameter are:

- SHA256128
- MD596
- SHA196
- GCMAES128
- GCMAES192
- GCMAES256

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

### -Certificate
Specifies the certificate to be used in default store.
Applicable only if **AuthenticationMethod** parameter is set to MachineCert.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies a cipher transform constant.
The acceptable values for this parameter are:

- DES
- DES3
- AES128
- AES192
- AES256
- GCMAES128
- GCMAES192
- GCMAES256

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
Specifies the custom IKE IPsec policies.

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
Specifies the Diffie-Hellman (DH) group for the IPsec policy.

```yaml
Type: DHGroup
Parameter Sets: CustomPolicy
Aliases: 
Accepted values: None, Group1, Group2, Group14, ECP256, ECP384, Group24

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Destination
Specifies the destination end point of the S2S connection. 
Note: If the **Certificate** parameter is specified as PSK, then an IP address should be specified for this parameter as a fully qualified domain name (FQDN) will not work.

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
Specifies the EAP method if IkeLocalAuthenticationMethod is EAP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: EAP-TLS, EAP-PEAP, EAP-MSCHAPv2, 

Required: False
Position: Named
Default value: MSCHAPv2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableQoS
Indicates whether to enable Quality of Service (QoS) on an interface.

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
Specifies the encryption method for the IKE policy.

```yaml
Type: EncryptionMethod
Parameter Sets: CustomPolicy
Aliases: Encryption
Accepted values: DES, DES3, AES128, AES192, AES256

Required: False
Position: Named
Default value: 4
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionType
Specifies the type of encryption.

```yaml
Type: String
Parameter Sets: EncryptionType
Aliases: 
Accepted values: NoEncryption, RequireEncryption, OptionalEncryption, MaximumEncryption

Required: False
Position: Named
Default value: RequireEncryption
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Subnet
Specifies the IPv4 subnet that is routed on this connection with metrics.
You must specify the IPv4 subnet in the format of *IPv4Address/SubnetPrefixLength:RouteMetric*.
For example: 192.168.1.0/24:1

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
Specifies an array of IPv4 filters that trigger demand dial connections.

```yaml
Type: String[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IPv6Subnet
Specifies the IPv6 subnet that is routed on this connection with metrics.

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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IdleDisconnectSeconds
Specifies the time interval, in seconds, after which an idle connection is disconnected.
Unless you disable idle timeout, an idle connection is disconnected after this time interval is reached.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: IdleDurationSeconds, IdleDisconnectSec

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiateConfigPayload
Indicates whether to initiate Config payload negotiation.

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

### -IntegrityCheckMethod
Specifies the integrity method for the IPsec policy.

```yaml
Type: IntegrityCheckMethod
Parameter Sets: CustomPolicy
Aliases: OtherHashAlgorithm, FirstIntegrityAlgorithm
Accepted values: MD5, SHA1, SHA256, SHA384

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalIPv4
Specifies that the IPv4 address should be negotiated.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalIPv6
Specifies that the IPv6 address should be negotiated.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
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
Specifies the maximum amount of time, in seconds, before a connection is disconnected due to a network outage.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: NetworkOutageTimeSec
Accepted values: 3, 6, 9, 12, 15, 30, 60, 120, 240, 360, 720, 900

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberOfTries
Specifies the number of connection attempts. 
 
                        
If this parameter is specified as zero (0), then the connection is not retried if the first attempt fails.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 3
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
Specifies the password for the user name to be used for dialing the connection.
Applicable only if **AuthenticationMethod** parameter is set to EAP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistent
Indicates that a connection is not disconnected due to inactivity.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfsGroup
Specifies the PFS group in the IPsec policy.

```yaml
Type: PfsGroup
Parameter Sets: CustomPolicy
Aliases: PfsGroupId
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PostConnectionIPv4Subnet
Specifies the IPv4 subnet routes that are added to a site-to-site interface after the connection is established.
The values specified are not used to initiate the site-to-site VPN connection.

```yaml
Type: String[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromoteAlternate
Specifies an IP address that if successfully connected becomes the primary IP address, and the current primary IP address is moved to the alternate list.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Specifies the underlying protocol used for tunneling.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyModule
Accepted values: L2TP, IKEv2, Automatic

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResponderAuthenticationMethod
Specifies the authentication method to be used by the S2S initiator to validate the S2S responder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: MachineCertificates, PSKOnly, 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetryIntervalSeconds
Specifies the time interval, in seconds, to wait between retries.

```yaml
Type: UInt32
Parameter Sets: (All)
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
Specifies the amount of data, in kilobytes (KB), that can be transferred using a security association (SA).
When the limit is reached, the SA must be renegotiated.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: SaRenegotiationDataSizeKB, LifeTimeKiloBytes

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeTimeSeconds
Specifies the lifetime, in seconds, of a security association (SA).
The SA is no longer valid after this time interval.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: SaLifeTimeSec, LifeTimeSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the text of the shared secret to be used in the connection.
This parameter is only applicable only if the **AuthenticationMethod** parameter is set to PSK or the **ResponderAuthenticationMethod** parameter is set to PSK.

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
Specifies the user name to be used for the connection.
Applicable only if **AuthenticationMethod** parameter is set to EAP.

```yaml
Type: String
Parameter Sets: (All)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnS2SInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-VpnS2SInterface](./Add-VpnS2SInterface.md)

[Clear-VpnS2SInterfaceStatistics](./Clear-VpnS2SInterfaceStatistics.md)

[Connect-VpnS2SInterface](./Connect-VpnS2SInterface.md)

[Disconnect-VpnS2SInterface](./Disconnect-VpnS2SInterface.md)

[Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)

[Get-VpnS2SInterface](./Get-VpnS2SInterface.md)

[Get-VpnS2SInterfaceStatistics](./Get-VpnS2SInterfaceStatistics.md)

[Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

[Set-VpnS2SInterface](./Set-VpnS2SInterface.md)

