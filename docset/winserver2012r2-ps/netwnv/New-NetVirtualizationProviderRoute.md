---
external help file: MSFT_NetVirtualizationProviderRouteSettingData.cdxml-help.xml
Module Name: NetWNV
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/netwnv/new-netvirtualizationproviderroute?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetVirtualizationProviderRoute
---

# New-NetVirtualizationProviderRoute

## SYNOPSIS
Creates a Provider Route in a virtual network.

## SYNTAX

```
New-NetVirtualizationProviderRoute -InterfaceIndex <UInt32> -DestinationPrefix <String> -NextHop <String>
 [-Metric <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetVirtualizationProviderRoute** cmdlet creates a network route for a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization uses Provider Routes to direct network traffic on the physical network.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

To create a Provider Route, specify the subnet as an IP prefix, the interface, and the address for the next hop gateway.

## EXAMPLES

### Example 1: Create a Provider Route
```
PS C:\> New-NetVirtualizationProviderRoute -DestinationPrefix "0.0.0.0/0" -InterfaceIndex 23 -NextHop "192.168.1.1" -Metric 5
```

This command creates a Provider Route for all network addresses, as specified by the destination prefix 0.0.0.0/0, with a next hop gateway as specified.
The command defines the interface as by using the index 23 and specifies a metric value of 5.

### Example 2: Create a Provider Route for a subnet
```
PS C:\>New-NetVirtualizationProviderRoute -DestinationPrefix "10.1.2.0/24" -InterfaceIndex 13 -NextHop "10.1.2.23"
```

This command specifies a Provider Route for an interface with the index 13 for the subnet specified by using the destination prefix.
This prefix specifies the subnet of addresses from 10.1.2.0 to 10.1.2.
254.
The command specifies the next hop gateway as 10.1.2.23.

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
Specifies an IP prefix, as a string, for the destination network.
You can specify an IPv4 or IPv6 address.
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

### -InterfaceIndex
Specifies an index for the network interface that has hv_win8_2 Network Virtualization enabled.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationProviderRoute](./Get-NetVirtualizationProviderRoute.md)

[Remove-NetVirtualizationProviderRoute](./Remove-NetVirtualizationProviderRoute.md)

[Set-NetVirtualizationProviderRoute](./Set-NetVirtualizationProviderRoute.md)

