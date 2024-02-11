---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-bgppeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BgpPeer
---

# Set-BgpPeer

## SYNOPSIS
Updates the configuration of the specified BGP peer.

## SYNTAX

```
Set-BgpPeer [-Name] <String> [-LocalIPAddress <IPAddress>] [-PeerIPAddress <IPAddress>] [-LocalASN <UInt32>]
 [-PeerASN <UInt32>] [-OperationMode <OperationMode>] [-PeeringMode <PeeringMode>] [-HoldTimeSec <UInt16>]
 [-IdleHoldTimeSec <UInt16>] [-MaxAllowedPrefix <UInt32>] [-RoutingDomain <String>] [-PassThru] [-Force]
 [-ClearPrefixLimit] [-Weight <UInt16>] [-RouteReflectorClient <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BgpPeer** cmdlet updates the Border Gateway Protocol (BGP) peer configuration.
This cmdlet returns error information if errors occur while modifying the BGP peer configuration.

## EXAMPLES

### Example 1: Update the BGP peer configuration for the specified neighbor
```
PS C:\>Set-BgpPeer -Name "TenantSite1" -PeeringMode Automatic -PassThru
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite1      192.168.1.10        10.1.1.10           64512               Server              Connecting
```

This command updates and modifies the BGP peer configuration for the specified neighbor.

### Example 2: Update and modify the BGP peer configuration and prompt the user for confirmation
```
PS C:\>Set-BgpPeer -Name "TenantSite1" -OperationMode Mixed -PeeringMode Automatic -PassThru
Confirm
BGP peering session is active for peer TenantSite1. Do you want to apply settings and restart peering?
 [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite1      192.168.1.10        10.1.1.10           64512               Mixed               Connecting
```

This command prompts the user for confirmation and upon confirmation, updates and modifies the BGP peer configuration for the specified neighbor, which is active.

### Example 3: Update and modify the BGP peer configuration for the specified neighbor
```
PS C:\>Set-BgpPeer -RoutingDomain "Rd_002" -Name "Tenant1" -PeerASN 64515  -PassThru
Confirm
BGP peering session is active for RedTenant1 for routing domain Rd_002. Do you want to apply settings and restart
peering?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
Tenant1          14.1.1.10           192.168.1.2         64515               Mixed               Connecting
```

This command prompts the user for confirmation and upon confirmation, updates and modifies the BGP peer configuration for the specified neighbor of a specified routing domain in multi-tenant environment.

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

### -ClearPrefixLimit
Indicates that the cmdlet clears the maximum limit on prefixes learned from the peer.
The cmdlet will reset the prefix learning to an unlimited number.

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

### -HoldTimeSec
Specifies the configured value of the **HoldTime** parameter in seconds after which the BGP Session expires if no BGP message is received.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleHoldTimeSec
Specifies the configured value of the **IdleHoldTime** in seconds after which the BGP Session expires if no BGP message is received.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalASN
Specifies the local autonomous systems (AS) number of the BGP Router instance for this peer.

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

### -LocalIPAddress
Specifies the local BGP router's peering IP address.
It can be of IPv4 or IPv6 address type.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxAllowedPrefix
Specifies the maximum number of allowed IPv4 or IPv6 network prefixes that can be learned from the given neighbor.

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
Specifies the peer name for which the configuration is to be modified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PeerId, PeerName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationMode
Specifies the BGP router's mode of operation.
The acceptable values for this parameter are:
- Peering Initiator as well as peering acceptor
- Only acting as a passive peering request acceptor.

```yaml
Type: OperationMode
Parameter Sets: (All)
Aliases:
Accepted values: Mixed, Server

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

### -PeerASN
Specifies the neighbor BGP router's AS number.

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

### -PeerIPAddress
Specifies the neighbor BGP router's peering IP address.
Acceptable values are an IPv4 or IPv6 address type.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeeringMode
Specifies a value to configure peering mode for the given peer.
The acceptable values for this parameter are:

- Automatic
- Manual

```yaml
Type: PeeringMode
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteReflectorClient
Specifies whether peer is a client peer or non-client peer.

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

### -RoutingDomain
Specifies the user-defined unique alphanumeric identifier for the routing domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

Required: False
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

### -Weight
Specifies administrative preference assigned to the routes received from this peer.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

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

### System.Net.IPAddress

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.OperationMode

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.PeeringMode

### System.UInt16

### System.Nullable`1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#BgpPeerConfig

## NOTES

## RELATED LINKS

[Add-BgpPeer](./Add-BgpPeer.md)

[Get-BgpPeer](./Get-BgpPeer.md)

[Remove-BgpPeer](./Remove-BgpPeer.md)

[Set-BgpPeer](./Set-BgpPeer.md)

[Start-BgpPeer](./Start-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

[Remote Access Cmdlets](./remoteaccess.md)

