---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Stop-VM
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1A05B05B-DAAE-4982-9D27-21ED2714DD20
---

# Stop-VM

## SYNOPSIS
Shuts down, turns off, or saves a virtual machine.

## SYNTAX

### Name (Default)
```
Stop-VM [-ComputerName <String[]>] [-Name] <String[]> [-Force] [-Save] [-TurnOff] [-AsJob] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Stop-VM [-Force] [-Save] [-TurnOff] [-AsJob] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Stop-VM** cmdlet shuts down, turns off, or saves a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Stop-VM -Name TestVM
```

Shuts down virtual machine TestVM through the guest operating system.

### Example 2
```
PS C:\>Stop-VM -Name VM1 -Force
```

Shuts down virtual machine TestVM through the guest operating system, regardless of any unsaved application data.
Hyper-V gives the guest five minutes to save data, then forces a shutdown.
This shutdown can result in loss of unsaved data.

### Example 3
```
PS C:\>Stop-VM -Name TestVM -TurnOff
```

Turns off virtual machine TestVM.
This operation is equivalent to disconnecting the power from the virtual machine, and can result in loss of unsaved data.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual machine is to be shut down.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
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

### -Force
Specifies that the shutdown of the virtual machine is to be forced.
If the virtual machine has applications with unsaved data, the virtual machine has five minutes to save data and shut down.
If the virtual machine is locked, it is shut down immediately.

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

### -Name
Specifies the name of the virtual machine to be shut down.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VirtualMachine** object is to be passed through to the pipeline representing the virtual machine to be shut down.

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

### -Save
Specifies that the virtual machine is to be saved.

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

### -TurnOff
Specifies that the virtual machine is to be turned off.

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

### -VM
Specifies the virtual machine to be shut down.

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
None by default; **Microsoft.HyperV.PowerShell.VirtualMachine** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

