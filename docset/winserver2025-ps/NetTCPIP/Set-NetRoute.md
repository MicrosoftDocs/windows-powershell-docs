---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetRoute.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetRoute
---

# Set-NetRoute

## SYNOPSIS
Modifies an entry or entries in the IP routing table.

## SYNTAX

### ByName (Default)
```
Set-NetRoute [[-DestinationPrefix] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-NextHop <String[]>] [-AddressFamily <AddressFamily[]>] [-Protocol <Protocol[]>] [-PolicyStore <String>]
 [-IncludeAllCompartments] [-Publish <Publish>] [-RouteMetric <UInt16>] [-ValidLifetime <TimeSpan>]
 [-PreferredLifetime <TimeSpan>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetRoute -InputObject <CimInstance[]> [-Publish <Publish>] [-RouteMetric <UInt16>]
 [-ValidLifetime <TimeSpan>] [-PreferredLifetime <TimeSpan>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetRoute** cmdlet modifies entries in the IP routing table.
Specify routes to modify by using the **DestinationPrefix** parameter or the *NextHop* parameter.
You can also specify routes by using the Get-NetRoute cmdlet.
If you do not specify which routes to modify, the cmdlets modifies all of the routes on the computer.

IP routing is the process of forwarding a packet based on the destination IP address.
Routing occurs at TCP/IP hosts and at IP routers.
The sending host or router determines where to forward the packet.
To determine where to forward a packet, the host or router consults a routing table that is stored in memory.
When TCP/IP starts, it creates entries in the routing table.
You can add entries either manually or automatically.

For more information about routing, see Chapter 5 - [IP Routing](https://technet.microsoft.com/library/bb727001.aspx) in the TechNet library.

After you create an entry in the routing table, you cannot modify the destination prefix or the next hop value.
If necessary, use the Remove-NetRoute cmdlet to remove the entry, and then recreate it with the desired values by using the New-NetRoute cmdlet.

## EXAMPLES

### Example 1: Change the route metric
```
PS C:\>Set-NetRoute -RouteMetric 257
```

This command changes the route metric to 257.
This route is less preferred than routes that have the default value of 256.

### Example 2: Modify the preferred lifetime
```
PS C:\> $TimeSpan = New-TimeSpan -Days 1
PS C:\> Set-NetRoute -DestinationPrefix "192.168.0.0/24" -PreferredLifetime $TimeSpan
```

The first command uses the New-TimeSpan cmdlet to create a time span of one day, and then stores it in the **$TimeSpan** variable.
For more information, type `Get-Help New-TimeSpan`.

The second command changes the lifetime of the IP route that has the destination prefix 192.168.0.0/24.
The command specifies the object stored in the **$TimeSpan** variable as the new preferred lifetime.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families of IP routes.
The cmdlet modifies the family that you specify for the IP route.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByName
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -DestinationPrefix
Specifies an array of destination prefixes of IP routes.
The cmdlet modifies settings for this IP route.
A destination prefix contains an IP address prefix and a prefix length, separated by a slash (/).
A value of `0.0.0.0/0` for IPv4 or `::/0` for IPv6 indicates that the value of the *NextHop* parameter is a default gateway.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllCompartments
Indicates that the cmdlet includes routes from all configured network compartments.
If you do not specify this parameter, the cmdlet modifies only routes in the default network compartment.

```yaml
Type: SwitchParameter
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies an array of aliases of network interfaces.
The cmdlet modifies IP routes for the interfaces that have the aliases that you specify.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet modifies IP routes for the interfaces located at the indexes that you specify.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: ifIndex

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHop
Specifies an array of next hop values.
The cmdlet modifies the routes that have these values.
A value of 0.0.0.0 for IPv4 or :: for IPv6 indicates that the route is on the local subnet.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PolicyStore
Specifies a **PolicyStore** value.
The cmdlet changes the **PolicyStore** value to the value that you specify.
The acceptable values for this parameter are:

- ActiveStore.
The IP address information is valid.
- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

Specify ActiveStore only.

If you do not specify this parameter, the default entries are created in both the ActiveStore and the PersistentStore.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredLifetime
Specifies a preferred lifetime, as a **TimeSpan** object, of an IP route.
The cmdlet changes the lifetime to the value that you specify.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.
For more information, type `Get-Help New-TimeSpan`.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies an array of types of routing protocols.
The cmdlet changes the protocol to the value you specify.
The acceptable values for this parameter are:

- Bbn
- Bgp
- Dhcp
- Dvmrp
- Egp
- Eigrp
- EsIs
- Ggp
- Hello
- Icmp
- Idpr
- Igrp
- IsIs
- Local
- NetMgmt
- Ospf
- Rip
- Rpl
- Other

```yaml
Type: Protocol[]
Parameter Sets: ByName
Aliases:
Accepted values: Other, Local, NetMgmt, Icmp, Egp, Ggp, Hello, Rip, IsIs, EsIs, Igrp, Bbn, Ospf, Bgp, Idpr, Eigrp, Dvmrp, Rpl, Dhcp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publish
Specifies the publish setting of an IP route.
The cmdlet changes the publish value to the value that you specify.
The acceptable values for this parameter are:

- No.
Do not publish or advertise IP route information in router advertisements.
- Yes.
Publish and advertise IP route information with an infinite valid lifetime in router advertisements.
- Age.
Publish and advertise IP route information with a finite valid lifetime, in router advertisements.
Specify a valid lifetime by using the **ValidLifetime** parameter.

```yaml
Type: Publish
Parameter Sets: (All)
Aliases:
Accepted values: No, Age, Yes

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMetric
Specifies an integer route metric for an IP route.
The cmdlet changes the metric to the value that you specify.
To choose among multiple routes, the computer adds this value to the interface metric value.
The computer selects the route with the lowest combined value.
To modify the interface metric, use the Set-NetIPInterface cmdlet.

```yaml
Type: UInt16
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

### -ValidLifetime
Specifies a valid lifetime, as a **TimeSpan** object, for an IP route.
The cmdlet changes the lifetime to the value that you specify.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.

```yaml
Type: TimeSpan
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetPrefixPolicy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-TimeSpan](https://technet.microsoft.com/en-us/library/hh849950.aspx)

[Find-NetRoute](./Find-NetRoute.md)

[Get-NetRoute](./Get-NetRoute.md)

[New-NetRoute](./New-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetIPInterface](./Set-NetIPInterface.md)

