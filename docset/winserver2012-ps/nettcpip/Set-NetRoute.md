---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/set-netroute?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetRoute

## SYNOPSIS
Modifies an entry or entries in the IP routing table.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetRoute [[-DestinationPrefix] <String[]>] [-AddressFamily <AddressFamily[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>] [-InterfaceIndex <UInt32[]>] [-NextHop <String[]>]
 [-PassThru] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan>] [-Publish <Publish>]
 [-RouteMetric <UInt16>] [-ThrottleLimit <Int32>] [-ValidLifetime <TimeSpan>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetRoute [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-PreferredLifetime <TimeSpan>]
 [-Publish <Publish>] [-RouteMetric <UInt16>] [-ThrottleLimit <Int32>] [-ValidLifetime <TimeSpan>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetRoute** cmdlet modifies an entry or entries in the IP routing table.
This cmdlet has 2 types of parameters.
One set of parameters specifies the routing table entry or entries to be modified.
A destination prefix must be used and next hop address must be used as an identifier and additional properties may be included such as InterfaceIndex.
The second set of parameters modifies properties in that NetIPAddress object.
These properties include Type, PrefixLength, valid or preferred lifetime and skip as source.

IP routing is the process of forwarding a packet based on the destination IP address.
Routing occurs at a sending TCP/IP host and at an IP router. 

In each case, the IP layer at the sending host or router must decide where to forward the packet.
For IPv4, routers are also commonly referred to as gateways.
To make these decisions, the IP layer consults a routing table stored in memory.
Routing table entries are created by default when TCP/IP initializes, and entries can be added either manually or automatically.
When the computer is routing, the RouteMetric property is added to the InterfaceMetric property, described as a part of NetIPInterface.
This total value is used to decide the pass-through interface to send the forwarded packets.
For more information, see IP Routing on TechNethttp://technet.microsoft.com/library/bb727001.aspx.

NetRoute objects do not allow the DestinationPrefix or NextHop properties to be modified after creation.
To modify these values, remove the NetRoute object and re-create it using the New-NetRoute cmdlet.

Note: A gateway is a routing concept covered by the Get-NetRoute cmdlet.
For IP end points, the gateway specifies the forwarding or next hop IP address over which the set of addresses defined by the network destination and subnet mask are reachable.

Without parameters, the Get-NetRoute cmdlet modifies the routing table for all of the routes on the computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetRoute -RouteMetric 257
```

This example sets the **RouteMetric** parameter to 257, making the route less preferable than the default of 256.

### EXAMPLE 2
```
PS C:\>$timespan = ( New-TimeSpan -Days 1 )



PS C:\>Set-NetRoute -DestinationPrefix 192.168.0.0/24 -PreferredLifetime $timespan
```

This example sets the **PreferredLifetime** parameter to one (1) day.

## PARAMETERS

### -AddressFamily
Specifies the IP address family of the IP route.
The acceptable values for this parameter are:

 -- IPv4: IPv4 route information. 

 -- IPv6: IPv6 route information.

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
Specifies the IP route information by the destination orefix.
This parameter value contains an IP address prefix and a prefix length, separated by a slash (/).
A destination prefix of `0.0.0.0/0` for IPv4 or `::/0` for IPv6 would indicate that the **NextHop** parameter value is a default gateway.

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
Specifies the interface on which the IP route is configured, as defined by the InterfaceAlias property.

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
Specifies the interface on which the IP route is configured, as defined by the InterfaceIndex number.

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
Specifies the next hop used in the IP route.
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
Modifies the preferred lifetime of the IP route.
This parameter value uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

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

### -Publish
Modifies the publish setting of the IP route.
The acceptable values for this parameter are:

 -- No: The IP Route information is not published nor advertised in router advertisements. 

 -- Yes: The IP Route information is published and advertised in router advertisements with an infinite **ValidLifetime** parameter. 

 -- Age: The IP Route information is published and advertised in router advertisements with a finite **ValidLifetime** parameter. 

The default value is No.

```yaml
Type: Publish
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMetric
Modifies the metric associated with the IP route.
This parameter value specifies an integer cost metric for the route.
This parameter value is added to the **InterfaceMetric** parameter value and the total value is used when choosing among multiple routes in the routing table that most closely match the destination address of a packet being forwarded.
The route with the lowest, combined RouteMetric property and InterfaceMetric property value is chosen.

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
Modifies the valid lifetime of a route.
This parameter value uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetPrefixPolicy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetRoute](./Get-NetRoute.md)

[New-NetRoute](./New-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[New-TimeSpan](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan)

