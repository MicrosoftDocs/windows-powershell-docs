---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 542F8548-9E57-40FB-96C4-5146BC806DCE
manager: dansimp
---

# Set-VpnS2SInterface

## SYNOPSIS
Modifies parameters for a site-to-site (S2S) interface.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VpnS2SInterface [-Name] <String> [-AdminStatus <Boolean>] [-AsJob] [-AuthenticationMethod <String>]
 [-Certificate <X509Certificate2>] [-CimSession <CimSession[]>] [-Destination <String[]>] [-EapMethod <String>]
 [-EncryptionType <String>] [-IdleDisconnectSeconds <UInt32>] [-InternalIPv4 <Boolean>]
 [-InternalIPv6 <Boolean>] [-IPv4Subnet <String[]>] [-IPv6Subnet <String[]>]
 [-NetworkOutageTimeSeconds <UInt32>] [-NumberOfTries <UInt32>] [-PassThru] [-Password <String>]
 [-PromoteAlternate <Boolean>] [-ResponderAuthenticationMethod <String>] [-RetryIntervalSeconds <UInt32>]
 [-SADataSizeForRenegotiationKilobytes <UInt32>] [-SALifeTimeSeconds <UInt32>] [-SharedSecret <String>]
 [-ThrottleLimit <Int32>] [-UserName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VpnS2SInterface [-Name] <String> [-AdminStatus <Boolean>] [-AsJob] [-AuthenticationMethod <String>]
 [-AuthenticationTransformConstants <AuthenticationTransformConstants>] [-Certificate <X509Certificate2>]
 [-CimSession <CimSession[]>] [-CipherTransformConstants <CipherTransformConstants>] [-Destination <String[]>]
 [-DHGroup <DHGroup>] [-EapMethod <String>] [-EncryptionMethod <EncryptionMethod>]
 [-IdleDisconnectSeconds <UInt32>] [-IntegrityCheckMethod <IntegrityCheckMethod>] [-InternalIPv4 <Boolean>]
 [-InternalIPv6 <Boolean>] [-IPv4Subnet <String[]>] [-IPv6Subnet <String[]>]
 [-NetworkOutageTimeSeconds <UInt32>] [-NumberOfTries <UInt32>] [-PassThru] [-Password <String>]
 [-PfsGroup <PfsGroup>] [-PromoteAlternate <Boolean>] [-ResponderAuthenticationMethod <String>]
 [-RetryIntervalSeconds <UInt32>] [-SADataSizeForRenegotiationKilobytes <UInt32>] [-SALifeTimeSeconds <UInt32>]
 [-SharedSecret <String>] [-ThrottleLimit <Int32>] [-UserName <String>] [-CustomPolicy] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VpnS2SInterface** cmdlet modifies parameters for a site-to-site (S2S) interface.
If the connection already exists, then the changes take effect after disconnection.

Use the **CustomPolicy** parameter to customize IPsec settings.
If the protocol is Automatic, then the only authentication method allowed is user name.
If the **AuthenticationMethod** parameter is set to pre-shared key (PSK), then only one interface can be enabled per destination and the initiator and responder policies are governed by what is specified for each interface.
If the **AuthenticationMethod** parameter is set to user name or computer certificates (machine certificates), then only the initiator policies are governed by what is specified for each interface and the responder policies are governed by what is specified on the server.

For incoming connections. 

 -- If the **AuthenticationMethod** parameter is set to PSK, then the interface for which the destination IP address matches the incoming IP address is activated. 

 -- If the **AuthenticationMethod** parameter is set to user name, then the interface for which the name matches the user name is activated. 

 -- If the **AuthenticationMethod** parameter is certificates, then the interface for which the name matches the certificate subject name is activated.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-VpnS2SInterface -Name edge1 -Destination 131.107.0.4 -PassThru
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet 
----                 -----------          -----------  --------------- ---------- 
edge1                {131.107.0.4}        True         Disconnected    {10.0.0.0/24:100}
```

This example modifies the destination address for the interface named edge1.

### EXAMPLE 2
```
PS C:\>Set-VpnS2SInterface -Name edge1 -AuthenticationMethod EAP -EapMethod EAP-MSCHAPv2 -PassThru
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet 
----                 -----------          -----------  --------------- ---------- 
EDGE1                {131.107.0.4}        True         Disconnected    {10.0.0.0/24:100}
```

This example modifies the initiator authentication method.

### EXAMPLE 3
```
PS C:\>Get-VpnS2SInterface -Name edge1 | Set-VpnS2SInterface -ResponderAuthenticationMethod MachineCertificates -PassThru
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet 
----                 -----------          -----------  --------------- ---------- 
EDGE1                {131.107.0.4}        True         Disconnected    {10.0.0.0/24:100}
```

This example modifies the responder authentication method for edge1.

### EXAMPLE 4
```
PS C:\>$cert1 = ( Get-ChildItem -Path cert:LocalMachine\My | Where-Object -FilterScript { $_.Subject -Like "*CN=edge1.contoso.com" } )



PS C:\>Set-VpnS2SInterface -Name 3-edge1 -AuthenticationMethod MachineCertificates -Certificate $cert1 -ResponderAuthenticationMethod MachineCertificates -PassThru
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet 
----                 -----------          -----------  --------------- ---------- 
3-edge1              {131.107.0.30}       True         Disconnected    {10.6.0.0/24:2}
```

This example changes the authentication method for the interface 3-edge1 to computer certificate and specifies the certificate for which the subject name matches edge1.contoso.com.

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

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: EAP
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticationTransformConstants
Specifies the authentication transform in the IPsec policy.

```yaml
Type: AuthenticationTransformConstants
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Certificate
Specifies the subject name of the certificate to use in the default store.
Applicable only if the **AuthenticationMethod** parameter is set to MachineCert.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CipherTransformConstants
Specifies the cipher in the IPsec policy.

```yaml
Type: CipherTransformConstants
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomPolicy
Specifies the custom IKE IPsec policies, must be a separate parameter set.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DHGroup
Specifies the Diffie-Hellman (DH) group in the IPsec policy.

```yaml
Type: DHGroup
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

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
Aliases: 

Required: False
Position: Named
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

Required: False
Position: Named
Default value: MSCHAPv2
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies the encryption method in the IKE policy.

```yaml
Type: EncryptionMethod
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: RequireEncryption
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Subnet
Specifies the IPv4 subnet that is routed on this connection with metrics.

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

### -IPv6Subnet
Specifies the IPv6 subnet that is routed on this connection with metrics.

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

### -IdleDisconnectSeconds
Specifies the time, in seconds, after which an idle connection is disconnected.
Unless the idle time-out is Disabled, the entire connection is disconnected if the connection is idle for the specified interval.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 300
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IntegrityCheckMethod
Specifies the integrity method in the IPsec policy.

```yaml
Type: IntegrityCheckMethod
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

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
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkOutageTimeSeconds
Specifies the maximum network outage time after which the connection is disconnected.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 15
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
Specifies the password for the user name to be used for the connection. 

Applicable only if the **AuthenticationMethod** parameter is set to EAP.

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

### -PfsGroup
Specifies the PFS group in the IPsec policy.

```yaml
Type: PfsGroup
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromoteAlternate
Specifies an alternate IP address that when it successfully connects becomes the primary IP address, and the current primary IP address is moved to the alternate list.

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

### -ResponderAuthenticationMethod
Specifies the authentication method to be used by the S2S initiator to validate the S2S responder.

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

### -RetryIntervalSeconds
Specifies the time, in seconds, between retries.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 60
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SADataSizeForRenegotiationKilobytes
Specifies the number of kilobytes that are allowed to transfer using a security association (SA).
After the limit is reached, then the SA will be renegotiated.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 10000
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeTimeSeconds
Specifies the lifetime of a SA in seconds, after which the SA is no longer valid.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 7200
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the text of the shared secret to be used for the connection.
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

### -UserName
Specifies the user name to be used for the connection.
Applicable only if the **AuthenticationMethod** parameter is set to EAP.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

[Get-VpnServerIPsecConfiguration](./Get-VpnServerIPsecConfiguration.md)

[Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

[Set-VpnServerIPsecConfiguration](./Set-VpnServerIPsecConfiguration.md)

