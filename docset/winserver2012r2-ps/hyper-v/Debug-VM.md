---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Debug-VM
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
ms.assetid: 3ACDD2AC-5C11-47FC-8DF8-3BF9F73C1DD8
---

# Debug-VM

## SYNOPSIS
Debugs a virtual machine.

## SYNTAX

### Name (Default)
```
Debug-VM [-ComputerName <String[]>] [-Name] <String[]> [-Force] [-AsJob] [-Passthru]
 [-InjectNonMaskableInterrupt] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Debug-VM [-Force] [-AsJob] [-Passthru] [-InjectNonMaskableInterrupt] [-VM] <VirtualMachine[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Debug-VM** cmdlet debugs a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> debug-vm "VM to Debug" -InjectNonMaskableInterrupt -Force
```

This example injects a non-maskable interrupt into the virtual machine named "VM to Debug".
A kernel debugger should be connected to the guest operating system before attempting to do this.

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

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet debugs the virtual machines on the hosts you specify.

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
Forces the command to run without asking for user confirmation.

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

### -InjectNonMaskableInterrupt
Indicates that the cmdlet sends a nonmaskable interrupt (NMI) to the virtual machine.
An interrupt handler must process a nonmaskable interrupt.

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
Specifies an array of names of virtual machines to be debugged.

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

### -VM
Specifies an array of virtual machine objects that are to be debugged.
To obtain virtual machine objects, use the Get-VM cmdlet.

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

## NOTES

## RELATED LINKS

