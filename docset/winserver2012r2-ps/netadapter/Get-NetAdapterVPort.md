---
external help file: MSFT_NetAdapterVPort.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
online version: 
schema: 2.0.0
title: Get-NetAdapterVPort
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8D323C9D-EE85-4390-A4D9-D10D69FA3486
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetAdapterVPort

## SYNOPSIS
Displays the network adapter virtual port (VPort) settings for a Single-Root I/O Virtualization (SR-IOV) or virtual machine queue (VMQ) VPort.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterVPort [[-Name] <String[]>] [-VPortID <UInt32[]>] [-SwitchID <UInt32[]>] [-FunctionID <UInt16[]>]
 [-PhysicalFunction] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterVPort -InterfaceDescription <String[]> [-VPortID <UInt32[]>] [-SwitchID <UInt32[]>]
 [-FunctionID <UInt16[]>] [-PhysicalFunction] [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterVPort** cmdlet displays the network adapter virtual port (VPort) settings for a Single-Root I/O Virtualization (SR-IOV) or virtual machine queue (VMQ) VPort.

Without a VPort specified, this cmdlet displays all VPorts on the network adapter with the port name, number and state.

Providing a specific VPort ID will display that specific VPort in long format.

Optionally, this cmdlet displays the SR-IOV virtual function (VF) settings, if the function ID is provided.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetAdapterVPort -Name "Ethernet 2"
```

This example displays all VPorts on network adapter named Ethernet 2.

### EXAMPLE 2
```
PS C:\> Get-NetAdapterVPort -Name "Ethernet 2" -VPortID 3
```

This example displays the VPort summary for VPort 3 on the network adapter named Ethernet Connection 2.

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

### -FunctionID
Specifies the ID of the SR-IOV VF settings to display.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: VfID

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

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

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalFunction
Specifies the physical function (PF) as the network adapter for the VPort.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: PF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchID
Specifies the virtual switch ID to identify which network adapter for one or more VPorts.

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

### -VPortID
Specifies the virtual switch port number that will be displayed in long format. 

Without this parameter, all VPorts or the specified range are displayed.
Specifying a VPort will display long format for a single VPort.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterVPortSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetAdapterSriov](./Get-NetAdapterSriov.md)

[Get-NetAdapterVmq](./Get-NetAdapterVmq.md)

