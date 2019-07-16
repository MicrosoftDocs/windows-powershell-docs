---
external help file: NetWNV_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: B3F7199E-ABD2-4D9C-BACD-30582E312C32
manager: dansimp
---

# Remove-NetVirtualizationCustomerRoute

## SYNOPSIS
Removes virtual network routes.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetVirtualizationCustomerRoute [-AsJob] [-CimSession <CimSession[]>] [-DestinationPrefix <String[]>]
 [-Metric <UInt32[]>] [-NextHop <String[]>] [-PassThru] [-RoutingDomainID <String[]>] [-ThrottleLimit <Int32>]
 [-VirtualSubnetID <UInt32[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetVirtualizationCustomerRoute [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Remove-NetVirtualizationCustomerRoute** cmdlet removes virtual network routes in a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
This cmdlet deletes Customer Routes that Network Virtualization uses on a virtual network.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can use the Get-NetVirtualizationCustomerRoute cmdlet to get routes to remove, or you can use any combination of the following values to specify which routes to remove: 

- Destination prefix.
A range of IP addresses as an IP prefix.
- Next hop.
A next hop gateway for the specified destination addresses.
- Routing domain ID.
An ID for a virtual network that can include multiple virtual subnets. 
- Virtual subnet ID.
An ID for a virtual subnet. 
- Route metric.
A value that routing uses to select from possible routes.

To manage virtual network routes, you can use the Set-NetVirtualizationCustomerRoute to modify the metric value, but you cannot change any of the other values in a route.
You can remove routes, and then use the New-NetVirtualizationCustomerRoute cmdlet to replace them.

## EXAMPLES

### Example 1: Remove a Customer Route
```
PS C:\>Remove-NetVirtualizationCustomerRoute -DestinationPrefix "172.16.0.0/16"
```

This command removes a Customer Route that has the specified destination prefix.

### Example 2: Remove Customer Routes for a gateway
```
PS C:\>Get-NetVirtualizationCustomerRoute -NextHop "172.16.0.1" | Remove-NetVirtualizationCustomerRoute
```

This command uses the Get-NetVirtualizationCustomerRoute to get all the Customer Routes that have a next hop gateway of 172.16.0.1.
The command passes them by using the pipe operator to the Remove-NetVirtualizationCustomerRoute cmdlet, which removes them.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -DestinationPrefix
Specifies an array of IP prefixes, as strings, for destination networks.
You can specify IPv4 and IPv6 addresses.
Use prefix notation: **0.0.0.0/0**.

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

### -Metric
Specifies an array of integer values for the metrics of routes.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHop
Specifies an array of IP addresses for next hop gateways for routes.

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

### -RoutingDomainID
Specifies an array of IDs for routing domains.
Routing domains use a GUID style ID: **{11111111-2222-3333-4444-000000000000}**.

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

### -VirtualSubnetID
Specifies an array of IDs for virtual subnets.
The acceptable values for this parameter are:integers from 4096 through 16777214.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationCustomerRoute](./Get-NetVirtualizationCustomerRoute.md)

[New-NetVirtualizationCustomerRoute](./New-NetVirtualizationCustomerRoute.md)

[Set-NetVirtualizationCustomerRoute](./Set-NetVirtualizationCustomerRoute.md)

