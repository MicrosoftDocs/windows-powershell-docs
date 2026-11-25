---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRouter_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-bgprouter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BgpRouter
---

# Set-BgpRouter

## SYNOPSIS
Updates the configuration of the local BGP router for the specified tenant ID.

## SYNTAX

```
Set-BgpRouter [-BgpIdentifier <IPAddress>] [-LocalASN <UInt32>] [-CompareMEDAcrossASN <Boolean>]
 [-DefaultGatewayRouting <Boolean>] [-IPv6Routing <IPv6RoutingState>] [-RoutingDomain <String>] [-PassThru]
 [-Force] [-LocalIPv6Address <IPAddress>] [-TransitRouting <TransitRouting>] [-RouteReflector <RouteReflector>]
 [-ClusterId <UInt32>] [-ClientToClientReflection <ClientToClientReflection>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BgpRouter** cmdlet updates the local Border Gateway Protocol (BGP) router configuration.
Error information will be returned if errors occur while modifying the BGP router configuration.

## EXAMPLES

### Example 1: Set the local BGP router with confirmation
```
PS C:\>Set-BgpRouter -LocalASN 64513 -PassThru
Confirm
One or more BGP peering sessions are active. Applying changes will restart these sessions. Do you want to continue?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

RoutingDomain         :
BgpIdentifier         : 192.168.1.10
LocalASN              : 64513
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command prompts the user for confirmation and on confirmation from user, updates, and then modifies the configuration of the local BGP router and restarts all the active BGP peerings.

### Example 2: Update and modify the local BGP router
```
PS C:\>Set-BgpRouter -LocalASN 64513 -Force -PassThru
RoutingDomain         :
BgpIdentifier         : 192.168.1.10
LocalASN              : 64513
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command updates and modifies the configuration of the local BGP router and restarts all the active BGP Peerings.

### Example 3: Update and modify the configuration of a BGP router for the specified routing domain
```
PS C:\>Set-BgpRouter -RoutingDomain Rd_001 -BgpIdentifier 14.1.1.10 -LocalASN 64522 -PassThru
RoutingDomain         : Rd_001
BgpIdentifier         : 14.1.1.10
LocalASN              : 64522
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command updates and modifies the configuration of the BGP router for the specified routing domain in Multi-tenant environment and restarts all the active BGP peerings.

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

### -BgpIdentifier
Specifies the local BGP Router Identifier.
The acceptable value for this parameter is an IPv4 address.

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

### -ClientToClientReflection
Specifies whether client to client reflection is enabled.

```yaml
Type: ClientToClientReflection
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClusterId
Specifies the cluster ID of the cluster.

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

### -CompareMEDAcrossASN
Indicates that comparison of Microsoft Enterprise Desktop (MED) values across different autonomous systems (AS) is enabled.

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

### -DefaultGatewayRouting
Indicates that routing of the unresolvable routes to the default (Internet) gateway is enabled or disabled.

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

### -IPv6Routing
Specifies whether to enable or disable IPv6 routing for this BGP router.

```yaml
Type: IPv6RoutingState
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalASN
Specifies the local AS Number of the BGP Router instance.

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

### -LocalIPv6Address
Specifies the local BGP router's global or site-local IPv6 Address, which is to be used as the NEXT-HOP value in the IPv6 route advertisements.

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

### -RouteReflector
Specifies whether BGP router will act as a RouteReflector.

```yaml
Type: RouteReflector
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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

### -TransitRouting
Specifies whether Transit routing is enabled.

```yaml
Type: TransitRouting
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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

### System.Net.IPAddress

### System.UInt32

### System.Boolean

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.IPv6RoutingState

### System.String

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.TransitRouting, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.RouteReflector, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.ClientToClientReflection, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#BgpRouterConfig

## NOTES

## RELATED LINKS

[Add-BgpRouter](./Add-BgpRouter.md)

[Get-BgpRouter](./Get-BgpRouter.md)

[Remove-BgpRouter](./Remove-BgpRouter.md)

[Remote Access Cmdlets](./remoteaccess.md)

