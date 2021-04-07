---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationCustomerRouteSettingData.cdxml-help.xml
manager: jasgro
Module Name: NetWNV
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/netwnv/new-netvirtualizationcustomerroute?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetVirtualizationCustomerRoute
---

# New-NetVirtualizationCustomerRoute

## SYNOPSIS
Creates a virtual network route.

## SYNTAX

```
New-NetVirtualizationCustomerRoute -RoutingDomainID <String> -VirtualSubnetID <UInt32>
 -DestinationPrefix <String> -NextHop <String> [-Metric <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetVirtualizationCustomerRoute** cmdlet creates a virtual network route in a Microsoft® Hyper-V® Server 2016 virtual network.
Network Virtualization allows for more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine by using a Customer Address in the virtual network.
Network Virtualization uses Customer Routes to manage network traffic on a virtual network.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

To create a virtual network route, specify the following values: 

- Destination prefix.
A range of IP addresses as an IP prefix.
- Next hop.
A next hop gateway for the specified destination addresses.
- Routing domain ID.
An ID for a virtual network that can include multiple virtual subnets. 
- Virtual subnet ID.
An ID for a virtual subnet.

You can also specify a metric rank.
Network Virtualization uses this rank to select a preferred route from several possible routes.
You can use the Set-NetVirtualizationCustomerRoute cmdlet to set or change this value later.

## EXAMPLES

### Example 1: Create a Customer Route
```
PS C:\>New-NetVirtualizationCustomerRoute -DestinationPrefix "172.16.0.0/16" -NextHop "172.16.0.1" -RoutingDomainID "{11111111-2222-3333-4444-000000000000}" -VirtualSubnetID 8392
```

This command creates a Customer Route.
The command specifies a destination prefix, a next hop gateway, a routing domain ID, and a virtual subnet ID.

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

### -DestinationPrefix
Specifies an IP prefix, as a string, for a destination network.
You can use an IPv4 or IPv6 address.
Use prefix notation: **0.0.0.0/0**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metric
Specifies an integer value for the route.
Network Virtualization selects the route that has the lowest metric value from a group of usable routes.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHop
Specifies an IP address for the next hop gateway for this route.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingDomainID
Specifies the ID for a routing domain.
A routing domain allows for routing among its multiple virtual subnets.
Routing domains use a GUID style ID: **{11111111-2222-3333-4444-000000000000}**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
Specifies the ID for a virtual subnet.
The acceptable values for this parameter are: integers from 4096 through 16777214.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationCustomerRoute](./Get-NetVirtualizationCustomerRoute.md)

[Remove-NetVirtualizationCustomerRoute](./Remove-NetVirtualizationCustomerRoute.md)

[Set-NetVirtualizationCustomerRoute](./Set-NetVirtualizationCustomerRoute.md)

