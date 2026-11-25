---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationProviderRouteSettingData.cdxml-help.xml
Module Name: NetWNV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netwnv/get-netvirtualizationproviderroute?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetVirtualizationProviderRoute
---

# Get-NetVirtualizationProviderRoute

## SYNOPSIS
Gets physical network routes for a virtualized network.

## SYNTAX

```
Get-NetVirtualizationProviderRoute [-InterfaceIndex <UInt32[]>] [-DestinationPrefix <String[]>]
 [-NextHop <String[]>] [-Metric <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetVirtualizationProviderRoute** cmdlet gets physical network routes for a Microsoft® Hyper-V® Server 2016 virtual network.
Network Virtualization allows for more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine by using a Customer Address in the virtual network.
Network Virtualization uses Provider Routes to direct network traffic on the physical network.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify Provider Routes by using any combination of the following: 

- Destination 
- Interface 
- Metric 
- Next hop gateway

## EXAMPLES

### Example 1: Get provider routes for a specified interface
```
PS C:\> Get-NetVirtualizationProviderRoute -InterfaceIndex 21
```

This command gets the provider routes for the interface that has the interface index 21.

### Example 2: Get provider routes for destination prefix
```
PS C:\>Get-NetVirtualizationProviderRoute -DestinationPrefix "172.16.0.0/16"
```

This command gets the provider routes that have the specified destination prefix.

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
Specifies an array of IP prefixes, as strings, for destination networks.
You can specify IPv4 and IPv6 addresses.
Use prefix notation: **0.0.0.0/0**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have Hyper-V Server 2016 Network Virtualization enabled.

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

### -Metric
Specifies an array of integer values.
Network Virtualization selects the route that has the lowest metric value from a group of usable routes.

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
Specifies an array of IP addresses for next hop gateways.

```yaml
Type: String[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-NetVirtualizationProviderRoute](./New-NetVirtualizationProviderRoute.md)

[Remove-NetVirtualizationProviderRoute](./Remove-NetVirtualizationProviderRoute.md)

[Set-NetVirtualizationProviderRoute](./Set-NetVirtualizationProviderRoute.md)

