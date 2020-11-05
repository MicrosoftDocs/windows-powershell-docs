---
external help file: MSFT_NetVirtualizationCustomerRouteSettingData.cdxml-help.xml
Module Name: NetWNV
online version: 
schema: 2.0.0
title: New-NetVirtualizationCustomerRoute
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B6372E82-9666-4E79-984A-65B9138D8477
ms.author: v-kaunu
ms.reviewer: brianlic
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
The **New-NetVirtualizationCustomerRoute** cmdlet creates a virtual network route in a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization uses Customer Routes to manage network traffic on a virtual network.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

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
Network Virtualization uses this rank to choose a preferred route from several possible routes.
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
Specifies an IP prefix, as a string, for a destination network.
You can use a IPv4 or IPv6 address.
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
Network Virtualization selects the route with the lowest metric value from a group of usable routes.

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
A routing domain allows routing among its multiple virtual subnets.
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
The acceptable values for this parameter are:integers from 4096 through 16777214.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationCustomerRoute](./Get-NetVirtualizationCustomerRoute.md)

[Remove-NetVirtualizationCustomerRoute](./Remove-NetVirtualizationCustomerRoute.md)

[Set-NetVirtualizationCustomerRoute](./Set-NetVirtualizationCustomerRoute.md)

