---
external help file: MSFT_NetVirtualizationProviderRouteSettingData.cdxml-help.xml
Module Name: NetWNV
online version: 
schema: 2.0.0
title: Set-NetVirtualizationProviderRoute
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3D5D931D-901C-4A70-B548-92C86FC62FEA
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Set-NetVirtualizationProviderRoute

## SYNOPSIS
Updates the metric for a Provider Route.

## SYNTAX

### ByName (Default)
```
Set-NetVirtualizationProviderRoute [-InterfaceIndex <UInt32[]>] [-DestinationPrefix <String[]>]
 [-NextHop <String[]>] [-Metric <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetVirtualizationProviderRoute -InputObject <CimInstance[]> [-Metric <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetVirtualizationProviderRoute** cmdlet updates the route metric for a route in a hv_win8_1 virtual network.
Network Virtualization allows more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine (VM) by using a Customer Address within the virtual network.
Network Virtualization ranks possible Provider Routes by using the metric value.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can use the Get-NetVirtualizationProviderRoute cmdlet to get routes to update, or you can specify Provider Routes by using any combination of the following: 

- Destination. 
- Interface. 
- Next hop gateway.

## EXAMPLES

### Example 1: Change a Provider Route metric
```
PS C:\> Set-NetVirtualizationProviderRoute -DestinationPrefix "0.0.0.0/0" -InterfaceIndex 17 -Metric 23 -NextHop "10.1.1.1"
```

This command specifies a Provider Route for the interface that has the index 17, with the specified destination prefix and next hop gateway.
The command resets the metric for this route to 23.

### Example 2: Change a Provider Route metric for a subnet
```
PS C:\>Set-NetVirtualizationProviderRoute -DestinationPrefix "10.10.0.0/16" -InterfaceIndex 23 -Metric 2
```

This command specifies a Provider Route for the interface that has the index 23 and the destination prefix 10.10.0.0/16.
The command changes the metric for this route to 2.

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
Parameter Sets: ByName
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
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have hv_win8_2 Network Virtualization enabled.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: 

Required: False
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
Specifies an array of IP addresses for next hop gateways.

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

[New-NetVirtualizationProviderRoute](./New-NetVirtualizationProviderRoute.md)

[Remove-NetVirtualizationProviderRoute](./Remove-NetVirtualizationProviderRoute.md)

