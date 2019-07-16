---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Start-VM
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
ms.assetid: DD7280C5-1F1A-45C7-8A40-2047AACE9053
---

# Start-VM

## SYNOPSIS
Starts a virtual machine.

## SYNTAX

### Name (Default)
```
Start-VM [-ComputerName <String[]>] [-Name] <String[]> [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Start-VM [-AsJob] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-VM** cmdlet starts a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Start-VM -Name TestVM
```

Starts virtual machine TestVM.

### Example 2
```
PS C:\>Start-VM -Name Test*
```

Starts all virtual machines whose names start with "Test."

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
Specifies one or more Hyper-V hosts on which a virtual machine is to be started.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be started.

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
Specifies that a **Microsoft.HyperV.PowerShell.VirtualMachine** object is to be passed through to the pipeline representing the virtual machine to be started.

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
Specifies the virtual machine to be started.

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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

###  
None by default; **Microsoft.HyperV.PowerShell.VirtualMachine** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

