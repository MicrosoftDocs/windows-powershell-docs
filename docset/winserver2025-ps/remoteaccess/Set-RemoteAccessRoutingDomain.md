---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessRoutingDomain_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-remoteaccessroutingdomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RemoteAccessRoutingDomain
---

# Set-RemoteAccessRoutingDomain

## SYNOPSIS
Configures S2S VPN settings for a routing domain configuration.

## SYNTAX

### EncryptionType (Default)
```
Set-RemoteAccessRoutingDomain [-Name] <String> [-InterimAccountingPeriodSec <UInt32>]
 [-IPAddressRange <String[]>] [-IPv6Prefix <String>] [-NetBiosIPAddress <IPAddress[]>]
 [-MaximumVpnConnections <UInt32>] [-TenantName <String[]>] [-PassThru] [-Force] [-EnableQoS <EnableQoS>]
 [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>] [-DnsIPAddress <IPAddress[]>]
 [-EncryptionType <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### CustomPolicy
```
Set-RemoteAccessRoutingDomain [-Name] <String> [-IdleDisconnectSec <UInt32>]
 [-InterimAccountingPeriodSec <UInt32>] [-IPAddressRange <String[]>] [-IPv6Prefix <String>]
 [-SaLifeTimeSec <UInt32>] [-MMSaLifeTimeSec <UInt32>] [-NetBiosIPAddress <IPAddress[]>]
 [-MaximumVpnConnections <UInt32>] [-TenantName <String[]>] [-PassThru] [-Force] [-EnableQoS <EnableQoS>]
 [-TxBandwidthKbps <UInt64>] [-RxBandwidthKbps <UInt64>] [-DnsIPAddress <IPAddress[]>] [-CustomPolicy]
 [-AuthenticationTransformConstant <AuthenticationTransformConstant>]
 [-CipherTransformConstant <CipherTransformConstant>] [-EncryptionMethod <EncryptionMethod>]
 [-IntegrityCheckMethod <IntegrityCheckMethod>] [-PfsGroup <PfsGroup>] [-SaRenegotiationDataSizeKB <UInt32>]
 [-DHGroup <DHGroup>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RemoteAccessRoutingDomain** cmdlet configures site to site (S2S) virtual private network (VPN) settings for a routing domain.

## EXAMPLES

### Example 1: Modify the configuration for a routing domain
```
PS C:\> Set-RemoteAccessRoutingDomain -RoutingDomain Rd_01 -IPAddressRange @("10.0.0.1","10.0.0.10") -Passthru


RoutingDomain                  : Rd_01
RoutingDomainID                : {11111111-1111-1111-1111-111111111001}
RoutingStatus                  : Enabled and Available
Capacity(Kbps)                 : 10240
IPAddressRange                 : {10.0.0.1 - 10.0.0.10}
IPv6Prefix                     : :: IdleDisconnect(s)              : 0
SADataSizeForRenegotiation(KB) : 0
SALifeTime(s)                  : 0
InterimAccounting(s)           : EncryptionType                 : NoEncryption
```

This command modifies configuration settings for a specified routing domain in a multitenant environment and displays the resulting configuration.

### Example 2: Modify configuration for IPv6 addresses and encryption
```
PS C:\> Set-RemoteAccessRoutingDomain -RoutingDomain Rd_01 -IPAddressRange @("10.0.0.1","10.0.0.10") -IPv6Prefix 3ffe::/64   -EncryptionType OptionalEncryption    -Passthru


RoutingDomain                  : Rd_01
RoutingDomainID                : {11111111-1111-1111-1111-111111111001}
RoutingStatus                  : Enabled and Available
Capacity(Kbps)                 : 10240
IPAddressRange                 : {10.0.0.1 - 10.0.0.10}
IPv6Prefix                     : 3ffe:: IdleDisconnect(s)              : 0
SADataSizeForRenegotiation(KB) : 0
SALifeTime(s)                  : 0
InterimAccounting(s)           : EncryptionType                 : OptionalEncryption
```

This command modifies configuration settings for a routing domain in a multitenant environment and displays the resulting configuration.

## PARAMETERS

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

### -AuthenticationTransformConstant
Specifies a transform constant.
The acceptable values for this parameter are:

- MD596
- SHA196
- SHA256128
- GCMAES128
- GCMAES192
- GCMAES256
- None

```yaml
Type: AuthenticationTransformConstant
Parameter Sets: CustomPolicy
Aliases:
Accepted values: MD596, SHA196, SHA256128, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CipherTransformConstant
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
- None

```yaml
Type: CipherTransformConstant
Parameter Sets: CustomPolicy
Aliases:
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomPolicy
Indicates that the interface uses custom Internet Key Exchange (IKE) IPsec policies.

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
Specifies the Diffie-Hellman (DH) group for the IKE policy.
The acceptable values for this parameter are:

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

### -DnsIPAddress
Specifies an array of IP addresses.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -EncryptionMethod
Specifies the encryption method for IKE policy.
The acceptable values for this parameter are:

- DES
- DES3
- AES128
- AES192
- AES256

```yaml
Type: EncryptionMethod
Parameter Sets: CustomPolicy
Aliases:
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

### -Force
Forces the command to run without asking for user confirmation.

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

### -IPAddressRange
Specifies an array of IP addresses to allocate to VPN clients.
The array consists of a beginning IP address and an ending IP address.

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

### -IPv6Prefix
Specifies the IPv6 prefix used for IPv6 address assignment.

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

### -IdleDisconnectSec
Specifies the time interval, in seconds, after which an idle connection is disconnected.
Unless you disable idle timeout, an idle connection is disconnected after this time interval is exceeded.

```yaml
Type: UInt32
Parameter Sets: CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IntegrityCheckMethod
Specifies an integrity check method for the IPsec policy.
The acceptable values for this parameter are:

- MD5
- SHA1
- SHA256
- SHA384

```yaml
Type: IntegrityCheckMethod
Parameter Sets: CustomPolicy
Aliases:
Accepted values: MD5, SHA1, SHA256, SHA384

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterimAccountingPeriodSec
Specifies a time interval, in seconds, for interim accounting.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MMSaLifeTimeSec


```yaml
Type: UInt32
Parameter Sets: CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumVpnConnections
Specifies the maximum number of concurrent VPN connections.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a routing domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName, RoutingDomain

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetBiosIPAddress
Specifies an array of IP addresses for NetBIOS names.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
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

### -PfsGroup
Specifies the PFS group in the IPsec policy.

- PFS1
- PFS2
- PFS2048
- ECP256
- ECP384
- PFSMM
- PFS24

```yaml
Type: PfsGroup
Parameter Sets: CustomPolicy
Aliases:
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RxBandwidthKbps
Specifies the receive, or ingress, bandwidth limit, in kilobits per second (Kbps).

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SaLifeTimeSec
Specifies the lifetime, in seconds, of a security association (SA).
The SA is no longer valid after this time interval.

```yaml
Type: UInt32
Parameter Sets: CustomPolicy
Aliases: QMSaLifeTimeSec

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaRenegotiationDataSizeKB
Specifies the amount of data, in kilobytes (KB), that can be transferred using a security association (SA).
When the limit is reached, the SA must be renegotiated.

```yaml
Type: UInt32
Parameter Sets: CustomPolicy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantName
Specifies an array of tenant names.

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
Specifies a transmit, or egress, bandwidth limit, in Kbps, for the interface.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.UInt32

### System.String[]

### System.Net.IPAddress[]

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.EnableQoS, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Nullable`1[[System.UInt64, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.AuthenticationTransformConstant

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.CipherTransformConstant

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.EncryptionMethod

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.IntegrityCheckMethod

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.PfsGroup

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessRoutingDomain.DHGroup

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#VpnRoutingDomainConfig

## NOTES

## RELATED LINKS

[Disable-RemoteAccessRoutingDomain](./Disable-RemoteAccessRoutingDomain.md)

[Enable-RemoteAccessRoutingDomain](./Enable-RemoteAccessRoutingDomain.md)

[Get-RemoteAccessRoutingDomain](./Get-RemoteAccessRoutingDomain.md)

