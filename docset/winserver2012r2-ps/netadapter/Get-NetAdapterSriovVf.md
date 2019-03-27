---
external help file: MSFT_NetAdapterSriovVf.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
online version: 
schema: 2.0.0
title: Get-NetAdapterSriovVf
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: DF76ED0C-3811-4C2B-9783-0DE952EC5841
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-NetAdapterSriovVf

## SYNOPSIS
Displays the Single-Root I/O Virtualization (SR-IOV) virtual function (VF) settings.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterSriovVf [[-Name] <String[]>] [-SwitchID <UInt32[]>] [-FunctionID <UInt16[]>] [-IncludeHidden]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterSriovVf -InterfaceDescription <String[]> [-SwitchID <UInt32[]>] [-FunctionID <UInt16[]>]
 [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterSriovVf** cmdlet displays the Single-Root I/O Virtualization (SR-IOV) virtual function (VF) settings. 
By default a table of VF settings will be displayed that includes the virtual function identifier (ID), virtual function name, network adapter ID, and the current MAC address.
Specifying a single VF will display that VF in more detail.
Additional displayed fields include the permanent MAC address, requester ID, and virtual port (VPort) information.

The network adapter to use is specified by either the name of the network adapter, interface description of the network adapter, or the switch ID of the virtual switch bound to the SR-IOV network adapter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetAdapterSriovVf -Name "Ethernet 1"
```

This example returns a list of the VFs with the VM names and MAC addresses for the network adapter named Wired Ethernet Connection 1.

### EXAMPLE 2
```
PS C:\> Get-NetAdapterSriovVf -SwitchId 2
```

This example returns a list of the VFs with the VM names and MAC addresses for the network adapter bound to virtual switch 2.

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
Specifies the VF ID number on the indicated network adapter to return more detailed information on the VF.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: VfID, Id

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

### -SwitchID
Specifies the virtual switch ID that identifies the network adapter for one or more VFs.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovVfSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterSriov](./Disable-NetAdapterSriov.md)

[Enable-NetAdapterSriov](./Enable-NetAdapterSriov.md)

[Get-NetAdapterSriov](./Get-NetAdapterSriov.md)

[Set-NetAdapterSriov](./Set-NetAdapterSriov.md)

