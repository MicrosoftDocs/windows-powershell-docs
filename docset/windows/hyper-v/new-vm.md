---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: kenwith
author: kenwith
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-VM
ms.reviewer:
ms.assetid: 99205277-D2BB-4879-ABC2-9FD1CA5BD2A5
ms.manager: dansimp
---

# New-VM

## SYNOPSIS
Creates a new virtual machine.

## SYNTAX

### No VHD (Default)
```
New-VM [[-Name] <String>] [[-MemoryStartupBytes] <Int64>] [-BootDevice <BootDevice>] [-NoVHD]
 [-SwitchName <String>] [-Path <String>] [-Version <Version>] [-Prerelease] [-Experimental]
 [[-Generation] <Int16>] [-Force] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### New VHD
```
New-VM [[-Name] <String>] [[-MemoryStartupBytes] <Int64>] [-BootDevice <BootDevice>] [-SwitchName <String>]
 -NewVHDPath <String> -NewVHDSizeBytes <UInt64> [-Path <String>] [-Version <Version>] [-Prerelease]
 [-Experimental] [[-Generation] <Int16>] [-Force] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Existing VHD
```
New-VM [[-Name] <String>] [[-MemoryStartupBytes] <Int64>] [-BootDevice <BootDevice>] [-SwitchName <String>]
 -VHDPath <String> [-Path <String>] [-Version <Version>] [-Prerelease] [-Experimental] [[-Generation] <Int16>]
 [-Force] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-VM** cmdlet creates a new virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> New-VM -Name "new 1" -MemoryStartupBytes 512MB
```

This example creates a new virtual machine named new 1 that has 512 MB of memory.

### Example 2
```
PS C:\> New-VM -Name "new 2" -MemoryStartupBytes 1GB -NewVHDPath d:\vhd\base.vhdx
```

This example creates a virtual machine named new 2 that has 1 GB of memory and that is connected to a new 40 GB virtual hard disk that uses the VHDX format.

### Example 3
```
PS C:\> New-VM -Name "new 3" -MemoryStartupBytes 1GB -VHDPath d:\vhd\BaseImage.vhdx
```

This example creates a virtual machine named new 3 that has 1 GB of memory and connects it to an existing virtual hard disk that uses the VHDX format.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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

### -BootDevice
Specifies the device to use as the boot device for the new virtual machine.
Allowed values are **CD**, **Floppy**, **LegacyNetworkAdapter**, **IDE**, NetworkAdapter, and VHD.

When LegacyNetworkAdapter is specified, this configures the new virtual machine with a network adapter that can be used to perform a PXE boot and install an operating system from a network installation server.

Note: Generation 2 virtual machines do not support Floppy, LegacyNetworkAdapter or IDE.
Using these values with a Generation 2 virtual machine will cause an error.

VHD and NetworkAdapter are new to Generation 2 virtual machines.
If you specify them on a Generation 1 virtual machine, then they are interpreted to be IDE and LegacyNetworkAdapter, respectively.

```yaml
Type: BootDevice
Parameter Sets: (All)
Aliases: 
Accepted values: Floppy, CD, IDE, LegacyNetworkAdapter, NetworkAdapter, VHD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be created.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Experimental


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

### -Force


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

### -Generation
Specifies the generation, as an integer, for the virtual machine.
The values that are valid in this version of Windows are 1 and 2.

```yaml
Type: Int16
Parameter Sets: (All)
Aliases: 
Accepted values: 1, 2

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryStartupBytes
Specifies the amount of memory, in bytes, to assign to the virtual machine.
The default value is 512 MB.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the new virtual machine.
The default name is New virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -NewVHDPath
Creates a new virtual hard disk with the specified path and connects it to the new virtual machine.
Absolute paths are allowed.
If only a file name is specified, the virtual hard disk is created in the default path configured for the host.

```yaml
Type: String
Parameter Sets: New VHD
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewVHDSizeBytes
Specifies the size of the dynamic virtual hard disk that is created and attached to the new virtual machine.

```yaml
Type: UInt64
Parameter Sets: New VHD
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoVHD
Creates a virtual machine without attaching any virtual hard disks.

```yaml
Type: SwitchParameter
Parameter Sets: No VHD
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the directory to store the files for the new virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prerelease


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

### -SwitchName
Specifies the friendly name of the virtual switch if you want to connect the new virtual machine to an existing virtual switch to provide connectivity to a network.
Hyper-V automatically creates a virtual machine with one virtual network adapter, but connecting it to a virtual switch is optional.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDPath
Specifies the path to a virtual hard disk file.

```yaml
Type: String
Parameter Sets: Existing VHD
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version


```yaml
Type: Version
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine

## NOTES

## RELATED LINKS

