---
external help file: PS_BgpRouter_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/remoteaccess/set-bgprouter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BgpRouter
---

# Set-BgpRouter

## SYNOPSIS
Modifies the local BGP router configuration.

## SYNTAX

```
Set-BgpRouter [-BgpIdentifier <IPAddress>] [-LocalASN <UInt32>] [-CompareMEDAcrossASN <Boolean>]
 [-DefaultGatewayRouting <Boolean>] [-IPv6Routing <IPv6RoutingState>] [-RoutingDomain <String>] [-PassThru]
 [-Force] [-LocalIPv6Address <IPAddress>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BgpRouter** cmdlet modifies the configuration of the local Border Gateway Protocol (BGP) router for a tenant.
You can modify the  IPv4 address of a local BGP router, specify whether the BGP router compares Multi-Exit Discriminator (MED) values across different autonomous systems, and specify whether the cmdlet enables routing of the unresolvable routes to the default gateway.
You can also modify the state of IPv6 routing for the BGP router and the IPv6 address of a local BGP router.

Use the Get-BgpRouter cmdlet to see the current settings.

## EXAMPLES

### Example 1: Modify the configuration of the local BGP router
```
PS C:\> Set-BgpRouter -LocalASN 64513 -PassThru



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

This command modifies the configuration of the local BGP router and restarts all the active BGP peerings.
The command specifies that the ASN of the local BGP router instance is 64513.
The command prompts the user for confirmation before it modifies the configuration of the router.
The command includes the **PassThru** parameter, so the command sends a **BgpRouterConfig** object to the console.

### Example 2: Modify the configuration of the local BGP router without confirmation
```
PS C:\> Set-BgpRouter -LocalASN 64513 -Force -PassThru



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

This command modifies the configuration of the local BGP router and restarts all the active BGP peerings.
The command specifies that the ASN of the local BGP router instance is 64513.
The command does not prompt the user for confirmation before it modifies the configuration of the router.

### Example 3: Modify the configuration of a BGP router in a routing domain
```
PS C:\> Set-BgpRouter -RoutingDomain "Rd_001" -BgpIdentifier 10.1.1.10 -LocalASN 64522 -PassThru




RoutingDomain         : Rd_001
BgpIdentifier         : 10.1.1.10
LocalASN              : 64522
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command modifies the configuration of the BGP router for the routing domain named Rd_001.
The command specifies the IP address of the local BGP router for the routing domain, and it specifies that the ASN of the local BGP router instance is 64522.

## PARAMETERS

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

### -BgpIdentifier
Specifies the IPv4 address of a local BGP router.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -CompareMEDAcrossASN
Indicates whether the BGP router compares Multi-Exit Discriminator (MED) values across different autonomous systems.

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
Indicates whether the cmdlet enables routing of the unresolvable routes to the default gateway.

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
Specifies the state of IPv6 routing for the BGP router.
The acceptable values for this parameter are:

- Enable
- Disable

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
Specifies the autonomous system number (ASN) for the local router.

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
Specifies the Internet IPv6 address of a local BGP router.
This parameter specifies the global or site-local Internet IPv6 address for the local BGP router.
The BGP router uses this IP address as the next hop value in the IPv6 route advertisements.

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

### -RoutingDomain
Specifies the name, as a string, of a routing domain.
The name of a routing domain is a user-defined alphanumeric string.
It must be unique.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpRouterConfig

## NOTES

## RELATED LINKS

[Get-BgpRouter](./Get-BgpRouter.md)

[Add-BgpRouter](./Add-BgpRouter.md)

[Remove-BgpRouter](./Remove-BgpRouter.md)

