---
external help file: NetWNV_Cmdlets.xml
Module Name: NetWNV
online version: https://learn.microsoft.com/powershell/module/netwnv/get-netvirtualizationcustomerroute?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetVirtualizationCustomerRoute

## SYNOPSIS
Gets virtual network routes.

## SYNTAX

```
Get-NetVirtualizationCustomerRoute [-AsJob] [-CimSession <CimSession[]>] [-DestinationPrefix <String[]>]
 [-Metric <UInt32[]>] [-NextHop <String[]>] [-RoutingDomainID <String[]>] [-ThrottleLimit <Int32>]
 [-VirtualSubnetID <UInt32[]>]
```

## DESCRIPTION
The **Get-NetVirtualizationCustomerRoute** cmdlet gets virtual network routes in a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within a virtual network.
This command gets Customer Routes that Network Virtualization use to manage traffic on a virtual network.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can use any combination of the following values to specify which routes to get: 

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

## EXAMPLES

### Example 1: Get a Customer Route
```
PS C:\>Get-NetVirtualizationCustomerRoute -DestinationPrefix "172.16.0.0/16"
```

This command gets a Customer Route that has the specified destination prefix.

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
You can specify both IPv4 and IPv6 addresses.
Use prefix notation: **0.0.0.0/0**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Metric
Specifies an array of integer values for the metrics of routes.

```yaml
Type: UInt32[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -RoutingDomainID
Specifies an array of IDs for routing domains.
Routing domains use a GUID style ID: **{11111111-2222-3333-4444-000000000000}**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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
Parameter Sets: (All)
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

[New-NetVirtualizationCustomerRoute](./New-NetVirtualizationCustomerRoute.md)

[Remove-NetVirtualizationCustomerRoute](./Remove-NetVirtualizationCustomerRoute.md)

[Set-NetVirtualizationCustomerRoute](./Set-NetVirtualizationCustomerRoute.md)

