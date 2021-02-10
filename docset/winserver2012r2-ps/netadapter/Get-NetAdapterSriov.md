---
external help file: MSFT_NetAdapterSriov.cdxml-help.xml
Module Name: NetAdapter
online version: 
schema: 2.0.0
title: Get-NetAdapterSriov
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: CD0DD608-637C-4E2F-A465-92C683337BB2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetAdapterSriov

## SYNOPSIS
Gets the Single-Root I/O Virtualization (SR-IOV) properties of the network adapter.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterSriov [[-Name] <String[]>] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterSriov -InterfaceDescription <String[]> [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterSriov** cmdlet gets the Single-Root I/O Virtualization (SR-IOV) properties of network adapters that support SR-IOV.
SR-IOV enables network traffic to by-pass the software switch layer of the Hyper-V virtualization stack.
As a result, the I/O overhead in the software emulation layer is diminished and can achieve network performance that is nearly the same performance as in non-virtualized environments.
Run this cmdlet to display how the hardware is set to support SR-IOV.
This cmdlet will display the properties of the network adapter that relate to SR-IOV, such as the number of ports, and virtual functions (VFs).
The property SriovSupport indicates potential reasons for SR-IOV not functioning properly.
The possible values for SriovSupport include the following. 

 - Unknown: Ensure that the computer has hardware support for SR-IOV and that I/O virtualization is enabled in the BIOS.
Also ensure that the computer is running Windows Server® 2012 and later. 

 - Supported: SR-IOV is supported and should be functioning properly. 

 - MissingAcs: SR-IOV cannot be used on this network adapter as the PCI Express hardware does not support Access Control Services (ACS).
This device may work in an alternate PCI Express slot.
Contact your hardware vendor for further information. 

 - MissingPfDriver: SR-IOV cannot be used on this network adapter as the device or device driver does not support SR-IOV.
If the network adapter supports SR-IOV, contact the hardware vendor for an updated driver. 

 - NoBusResources: SR-IOV cannot be used on this network adapter as there are not enough PCI Express bus numbers available. 

 - NoIoMmuSupport: SR-IOV cannot be used on this computer because of one or more of the following reasons. 

 - - The processor does not support second level address translation (SLAT).
For processors manufactured by Intel Corporation™ (Intel™), this feature might be referred to as Extended Page Tables (EPT).
For processors manufactured by Advanced Micro Devices™ (AMD™), this feature might be referred to as Rapid Virtualization Indexing (RVI) or Nested Page Tables (NPT). 

 - - The chipset on the computer does not do Interrupt and/or DMA remapping, without which SR-IOV cannot be supported. 

 - - This computer has been configured to disable the use of I/O remapping hardware. 

 - NoVfBarSpace: SR-IOV cannot be used on this network adapter as there are not enough PCI Express BAR resources available.
This may be due to incorrect or partial configuration in the computer BIOS for Interrupt and DMA remapping.
These settings may be referred to as SR-IOV or input/output memory management unit (IOMMU) support.
If the computer BIOS is correctly configured, this device may work in an alternate PCI Express slot.
Contact the original equipment manufacturer of the computer for further information. 

 - NoOscSupport: To use SR-IOV on this computer, the computer BIOS must be updated to allow Windows Server 2012 and later to control PCI Express using `_OSC HandOff`.
Contact the original equipment manufacturer of the computer for an update.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetAdapterSriov -Name *
```

This example displays the SR-IOV properties for all SR-IOV-capable network adapters.

### EXAMPLE 2
```
PS C:\>Get-NetAdapterSriov -Name "Ethernet 2"
```

This example displays the SR-IOV properties for network adapter named Ethernet 2.

### EXAMPLE 3
```
PS C:\>Get-NetAdapterSriov -InterfaceDescription "Contoso 12345 Gigabit Network Device"
```

This example displays the SR-IOV properties for the network adapter with the interface description Contoso 12345 Gigabit Network Device.

### EXAMPLE 4
```
PS C:\>Get-NetAdapterSriov -Name * | Where-Object -FilterScript { $_.Enabled -Eq $true }
```

This example gets the SR-IOV properties for the network adapter with SR-IOV enabled.

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

### -IncludeHidden
Specifies both visible and hidden network adapters.
If a wildcard character is used to identify a network adapter, then the wildcard character is matched against both hidden and visible adapters.

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
The name of the network adapter from which to retrieve the SR-IOV properties.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Disable-NetAdapterSriov](./Disable-NetAdapterSriov.md)

[Enable-NetAdapterSriov](./Enable-NetAdapterSriov.md)

[Get-NetAdapterSriovVf](./Get-NetAdapterSriovVf.md)

[Set-NetAdapterSriov](./Set-NetAdapterSriov.md)

