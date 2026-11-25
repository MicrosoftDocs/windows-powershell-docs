---
external help file: GatewaytunnelConfig_v1.0.cdxml-help.xml
Module Name: Gatewaytunnel
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/gatewaytunnel/set-gatewaytunnel?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-GatewayTunnel
---

# Set-GatewayTunnel

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Set-GatewayTunnel [-TunnelName] <String> [[-RoutingDomainName] <String>] [[-LocalIp] <String>]
 [[-RemoteIp] <String>] [[-TunnelIdentity] <String>] [[-Routes] <String>] [[-LocalExemptRoutes] <String>]
 [[-RemoteExemptRoutes] <String>] [-LocalSubnets <String>] [-Standby <Boolean>] [-AdminStatus <Boolean>]
 [-AutoConnectEnabled <Boolean>] [-ProtocolType <ProtocolType>] [-EncryptionType <EncryptionType>]
 [-IpsecEncryption <IpsecEncryption>] [-IpsecIntegrity <IpsecIntegrity>] [-Pfsgroup <Pfsgroup>]
 [-IkeEncryption <IkeEncryption>] [-IkeIntegrity <IkeIntegrity>] [-Dhgroup <Dhgroup>]
 [-MMSALifeTimeInSeconds <UInt32>] [-SALifeTimeInSeconds <UInt32>] [-SALifeKilloBytes <UInt32>]
 [[-SharedSecret] <String>] [-DpdTimeout <UInt32>] [-UseNarrowTrafficSelectors <Boolean>]
 [-IsConnectionNATed <Boolean>] [-ConnectReason <ConnectReason>] [-TunnelId <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AdminStatus
{{ Fill AdminStatus Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
{{ Fill AsJob Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoConnectEnabled
{{ Fill AutoConnectEnabled Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectReason
{{ Fill ConnectReason Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.ConnectReason
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, ServiceTriggered, DataTriggered, UserTriggered, RemoteTriggered, RemoteCrashTriggered

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Dhgroup
{{ Fill Dhgroup Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.Dhgroup
Parameter Sets: (All)
Aliases:
Accepted values: None, DhGroup1, DhGroup2, DhGroup14

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DpdTimeout
{{ Fill DpdTimeout Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: Dpd

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionType
{{ Fill EncryptionType Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.EncryptionType
Parameter Sets: (All)
Aliases:
Accepted values: NoEncryption, StrongEncryption, RequiredEncryption, OptionalEncryption, CustomEncryption

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IkeEncryption
{{ Fill IkeEncryption Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IkeEncryption
Parameter Sets: (All)
Aliases:
Accepted values: DES, DES3, AES128, AES192, AES256

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IkeIntegrity
{{ Fill IkeIntegrity Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IkeIntegrity
Parameter Sets: (All)
Aliases:
Accepted values: MD5, SHA1, SHA256, SHA384

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpsecEncryption
{{ Fill IpsecEncryption Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IpsecEncryption
Parameter Sets: (All)
Aliases: Encryption
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpsecIntegrity
{{ Fill IpsecIntegrity Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IpsecIntegrity
Parameter Sets: (All)
Aliases: Auth
Accepted values: MD5, SHA1, SHA256, GCMAES128, GCMAES192, GCMAES256

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsConnectionNATed
{{ Fill IsConnectionNATed Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalExemptRoutes
{{ Fill LocalExemptRoutes Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalIp
{{ Fill LocalIp Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: local

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalSubnets
{{ Fill LocalSubnets Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LocalSubnet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MMSALifeTimeInSeconds
{{ Fill MMSALifeTimeInSeconds Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: MMSALifeTime

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pfsgroup
{{ Fill Pfsgroup Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.Pfsgroup
Parameter Sets: (All)
Aliases: Pfs
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, MM, PFS24

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProtocolType
{{ Fill ProtocolType Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.ProtocolType
Parameter Sets: (All)
Aliases:
Accepted values: Ikev2, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoteExemptRoutes
{{ Fill RemoteExemptRoutes Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoteIp
{{ Fill RemoteIp Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: remote

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Routes
{{ Fill Routes Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Route

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomainName
{{ Fill RoutingDomainName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: customer

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeKilloBytes
{{ Fill SALifeKilloBytes Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: SALifeKb

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SALifeTimeInSeconds
{{ Fill SALifeTimeInSeconds Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: SALifeTime

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
{{ Fill SharedSecret Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Presharedkey

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Standby
{{ Fill Standby Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TunnelId
{{ Fill TunnelId Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MMProviderContextKey

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TunnelIdentity
{{ Fill TunnelIdentity Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TunnelName
{{ Fill TunnelName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseNarrowTrafficSelectors
{{ Fill UseNarrowTrafficSelectors Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Boolean

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.ProtocolType

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.EncryptionType

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IpsecEncryption

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IpsecIntegrity

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.Pfsgroup

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IkeEncryption

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.IkeIntegrity

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.Dhgroup

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PS_GatewayTunnel.ConnectReason

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#PS_GatewayTunnel

## NOTES

## RELATED LINKS
