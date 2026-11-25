---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRouter_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-bgprouter?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-BgpRouter
---

# Add-BgpRouter

## SYNOPSIS
Adds a BGP router for the specified Tenant ID.

## SYNTAX

```
Add-BgpRouter -BgpIdentifier <IPAddress> -LocalASN <UInt32> [-IPv6Routing <IPv6RoutingState>]
 [-CompareMEDAcrossASN <Boolean>] [-DefaultGatewayRouting <Boolean>] [-PassThru] [-Force]
 [-RoutingDomain <String>] [-LocalIPv6Address <IPAddress>] [-TransitRouting <TransitRouting>]
 [-RouteReflector <RouteReflector>] [-ClusterId <UInt32>]
 [-ClientToClientReflection <ClientToClientReflection>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpRouter** cmdlet adds a new Border Gateway Protocol (BGP) router for the given tenant. 
This cmdlet returns error information if errors occur while adding the BGP router.

## EXAMPLES

### Example 1: Add a local BGP router
```
PS C:\>Add-BgpRouter -BgpIdentifier 10.1.1.10-LocalASN 64522 -PassThru
RoutingDomain            : 
BgpIdentifier            : 10.1.1.10
LocalASN                 : 64522
CompareMEDAcrossASN      : False
DefaultGatewayRouting    : False
IPv6Routing              : Disabled
LocalIPv6Address         : 
PeerName                 : 
PolicyName               : 
TransitRouting           : Disabled
RouteReflector           : Disabled
ClusterId                : 
ClientToClientReflection :
```

This command adds a local BGP router.

### Example 2: Add a local BGP router for a specified routing domain
```
PS C:\>Add-BgpRouter -RoutingDomain Rd_001 -BgpIdentifier 10.1.1.10 -LocalASN 64522 -PassThru
RoutingDomain            : Rd_001
BgpIdentifier            : 10.1.1.10
LocalASN                 : 64522
CompareMEDAcrossASN      : False
DefaultGatewayRouting    : False
IPv6Routing              : Disabled
LocalIPv6Address         : 
PeerName                 : 
PolicyName               : 
TransitRouting           : Disabled
RouteReflector           : Disabled
ClusterId                :
ClientToClientReflection:
```

This command adds a local BGP router for the specified routing domain in a multi-tenant environment.

### Example 3: Add a local BGP router and make it a Route Reflector
```
PS C:\>Add-BgpRouter -BgpIdentifier 10.1.1.10 -LocalASN 64522 -RouteReflector Enabled -ClusterId 1234 -TransitRouting Enabled -ClientToClientReflection Disabled -PassThru
RoutingDomain                   : 
BgpIdentifier                   : 10.1.1.10
LocalASN                        : 64522
CompareMEDAcrossASN             : False
DefaultGatewayRouting           : False
IPv6Routing                     : Disabled
LocalIPv6Address                : 
PeerName                        : 
PolicyName                      : 
TransitRouting                  : 
EnabledRouteReflector           : Enabled
ClusterId                       : 1234
ClientToClientReflection        : Disabled
```

This command adds a local BGP router.

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
Specifies the local BGP Router identifier.
The acceptable value for this parameter is an IPv4 address.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
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
Specifies whether client to client reflection is enabled or disabled.

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
Specifies the cluster ID of the router reflector.

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
Indicates whether comparison of Microsoft Enterprise Desktop (MED) values across different autonomous systems (AS) are enabled.

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

### -DefaultGatewayRouting
Indicates whether routing of the unresolvable routes to the default (Internet) gateway is enabled or disabled.

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
Specifies a value that enables or disables IPv6 routing for this BGP router.
The acceptable values for this parameter are:

- Disable
- Enable

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
Specifies the local AS number of the BGP Router instance. See [AS numbers by IANA](https://www.iana.org/assignments/as-numbers/as-numbers.xhtml) for the list of 32 bit AS numbers.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalIPv6Address
Specifies the local BGP Router's global or site-local IPv6 address.
This value is used as the NEXT-HOP value in the IPv6 route advertisements.

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
Specifies whether BGP router acts as a route reflector.

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

### -TransitRouting
Specifies whether transit routing is enabled.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpRouterConfig

## NOTES

## RELATED LINKS

[Get-BgpRouter](./Get-BgpRouter.md)

[Remove-BgpRouter](./Remove-BgpRouter.md)

[Set-BgpRouter](./Set-BgpRouter.md)

[Remote Access Cmdlets](./remoteaccess.md)

