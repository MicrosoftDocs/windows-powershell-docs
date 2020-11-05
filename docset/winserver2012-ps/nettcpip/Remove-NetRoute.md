---
external help file: NetTCPIP_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 3252B6F3-7908-47F2-BEAB-BFE265B7C985
manager: dansimp
---

# Remove-NetRoute

## SYNOPSIS
Deletes an entry or entries (IP routes) from the IP routing table.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetRoute [[-DestinationPrefix] <String[]>] [-AddressFamily <AddressFamily[]>] [-AsJob]
 [-AssociatedIPInterface <CimInstance>] [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>]
 [-InterfaceIndex <UInt32[]>] [-NextHop <String[]>] [-PassThru] [-PolicyStore <String>]
 [-PreferredLifetime <TimeSpan[]>] [-Publish <Publish[]>] [-RouteMetric <UInt16[]>] [-ThrottleLimit <Int32>]
 [-ValidLifetime <TimeSpan[]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetRoute [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetRoute** cmdlet deletes an entry or entries from the IP routing table, including destination network prefixes, Next Hop IP addresses and Route Metrics.
Parameters can be used to specify a set of routes to delete.

IP routing is the process of forwarding a packet based on the destination IP address.
Routing occurs at a sending TCP/IP host and at an IP router. 

In each case, the IP layer at the sending host or router must decide where to forward the packet.
For IPv4, routers are also commonly referred to as gateways.
To make these decisions, the IP layer consults a routing table stored in memory.
Routing table entries are created by default when TCP/IP initializes, and entries can be added either manually or automatically.
When the computer is routing, the RouteMetric property is added to the InterfaceMetric property, described as a part of NetIPInterface.
This total value is used to decide the pass-through interface to send the forwarded packets.
For more information, see IP Routing on TechNethttp://technet.microsoft.com/library/bb727001.aspx.

Without parameters, the Get-NetRoute cmdlet deletes all of the routes on the server.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NetRoute
```

This example removes all of the IP routes on the computer, including default routes.

### EXAMPLE 2
```
PS C:\>Remove-NetRoute -NextHop 192.168.0.1
```

This example removes all of the IP routes that have a next hop of 192.168.0.1.

## PARAMETERS

### -AddressFamily
Removes all of the routes that have a specific IP address family.
The acceptable values for this parameter are:

 -- IPv4: Removes all IP routes that have an IPv4 address. 

 -- IPv6: Removes all IP routes that have an IPv6 address.

```yaml
Type: AddressFamily[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -AssociatedIPInterface
Removes all of the IP routes that are associated with a specific network IP interface CIM object.
This is typically as input through a pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -DestinationPrefix
Removes all of the IP routes that have a specific destination prefix.
This parameter value contains an IP address prefix and a prefix length, separated by a slash (/).
A destination prefix of `0.0.0.0/0` for IPv4 or `::/0` for IPv6 would indicate that the NextHop is a default gateway.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: Dhcp
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Removes all of the IP routes that are connected to a specific interface, described by the InterfaceAlias property.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Removes all of the IP routes that are connected to a specific interface, described by InterfaceIndex number.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHop
Removes all of the IP routes that have a specific next hop.
This parameter value is the IP address of the next hop in the route.
A next hop of `0.0.0.0` for IPv4 or `::` for IPv6 would indicate that the route is on-link.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Specifies the PolicyStore value.
The acceptable values for this parameter are:

 -- ActiveStore: The IP address information is currently valid. 

 -- PersistentStore: The IP address information is persistent across reboots.
When the computer starts, the PersistentStore settings are copied to the ActiveStore. 

The default value is ActiveStore.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredLifetime
Removes all of the IP routes that have a specific preferred lifetime.
This parameter value uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publish
Removes all of the IP routes that have a specific publish setting.
The acceptable values for this parameter are:

 -- Age: The IP Route information is published and advertised in router advertisements with an finite ValidLifetime. 

 -- No: The IP Route information is published and advertised in router advertisements with an infinite ValidLifetime.
This is the default. 

 -- Yes: The IP Route information is published and advertised in router advertisements with an infinite ValidLifetime.

```yaml
Type: Publish[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMetric
Removes all of the IP routes that have a specific route metric.
This parameter value specifies an integer cost metric for the route.
This parameter value is added to the **InterfaceMetric** parameter value and the total value is used when choosing among multiple routes in the routing table that most closely match the destination address of a packet being forwarded.
The route with the lowest, combined RouteMetric property and InterfaceMetric property value is chosen.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Removes all of the IP routes that have a specific valid lifetime.
This parameter value uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#rootStandardCimv2MSFT_NetRoute
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetRoute](./Get-NetRoute.md)

[New-NetRoute](./New-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

