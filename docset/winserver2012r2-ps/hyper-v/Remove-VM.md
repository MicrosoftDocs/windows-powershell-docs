---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VM
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 43E9854F-F085-4991-991A-89F8363CB4C0
---

# Remove-VM

## SYNOPSIS
Deletes a virtual machine.

## SYNTAX

### Name (Default)
```
Remove-VM [-ComputerName <String[]>] [-Name] <String[]> [-Force] [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Remove-VM [-Force] [-AsJob] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VM** cmdlet deletes a virtual machine.
Running this cmdlet deletes the virtual machine's configuration file, but does not delete any virtual hard drives.
If the virtual machine has any snapshots, these are deleted and merged into the virtual hard disk files after the virtual machine is deleted.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VM "new 1"
Confirm: Are you sure you want to remove virtual machine "new 1"?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

Removes virtual machine new 1.

### Example 2
```
PS C:\>Remove-VM -Name "new 2" -Force
```

Removes virtual machine new 2, suppressing the confirmation prompt.

### Example 3
```
PS C:\>Get-VM -Name New* | Remove-VM -Force
```

Removes with no confirmation prompt all virtual machines having names starting with New.

## PARAMETERS

### -AsJob
Specifies that this cmdlet is to be run as a background job.

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
Specifies one or more Hyper-V hosts from which the virtual machine is to be deleted.
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
Specifies that confirmation prompts are to be suppressed during deletion of the virtual machine.

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
Specifies the name of the virtual machine to be deleted.

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
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be deleted.

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
Specifies the virtual machine to be deleted.

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

