---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMBios
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: D898A362-ADB0-4B21-8A50-BE3224D6BE86
---

# Set-VMBios

## SYNOPSIS
Configures the BIOS of a Generation 1 virtual machine.

## SYNTAX

### VMName (Default)
```
Set-VMBios [-DisableNumLock] [-EnableNumLock] [-StartupOrder <BootDevice[]>] [-Passthru]
 [-ComputerName <String[]>] [-VMName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMBios
```
Set-VMBios [-VMBios] <VMBios[]> [-DisableNumLock] [-EnableNumLock] [-StartupOrder <BootDevice[]>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMBios [-DisableNumLock] [-EnableNumLock] [-StartupOrder <BootDevice[]>] [-Passthru]
 [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMBios** cmdlet configures the BIOS of a Generation 1 virtual machine.
Note: This cmdlet does not operate with Generation 2 virtual machine.
If attempted, the cmdlet throws an error.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMBios TestVM -DisableNumLock
```

This example disables the NumLock key by default on virtual machine TestVM.

### Example 2
```
PS C:\> Set-VMBios TestVM -StartupOrder @("Floppy", "LegacyNetworkAdapter", "CD", "IDE")
```

This example configures virtual machine TestVM to check for a boot device in the following order: floppy disk, network, CD drive, hard disk.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts for which the BIOS is to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
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

### -DisableNumLock
Specifies that NumLock is to be disabled in the BIOS of the virtual machine to be configured.

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

### -EnableNumLock
Specifies that NumLock is to be enabled in the BIOS of the virtual machine to be configured.

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

### -Passthru
Specifies that an **Microsoft.HyperV.PowerShell.Bios** object is to be passed through to the pipeline representing the BIOS to be configured.

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

### -StartupOrder
Specifies an array of boot devices representing the boot order in the BIOS of the virtual machine.
The boot devices are specified as members of the **BootDevices** enumeration (**CD**, **IDE**, **LegacyNetworkAdapter**, **Floppy**).

Note: The other BootDevices enumeration values of VHD and NetworkAdapter are for Generation 2 VMs only, and are not valid with this cmdlet.

```yaml
Type: BootDevice[]
Parameter Sets: (All)
Aliases: 
Accepted values: Floppy, CD, IDE, LegacyNetworkAdapter, NetworkAdapter, VHD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which the BIOS is to be configured.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMBios
Specifies an array of BIOS objects.
The cmdlet configures the BIOS that you specify for the virtual machines.
To obtain a BIOS object, use the Get-VMBios cmdlet.

```yaml
Type: VMBios[]
Parameter Sets: VMBios
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which the BIOS is to be configured.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.Bios** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

