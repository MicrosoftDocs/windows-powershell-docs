---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Import-VMInitialReplication
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
ms.assetid: DFCA9ECE-DCD3-4184-BBA1-F6A7457EE408
---

# Import-VMInitialReplication

## SYNOPSIS
Imports initial replication files for a Replica virtual machine to complete the initial replication when using external media as the source.

## SYNTAX

### VMName (Default)
```
Import-VMInitialReplication [-Path] <String> [-AsJob] [-ComputerName <String[]>] [-VMName] <String[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMReplication
```
Import-VMInitialReplication [-Path] <String> [-AsJob] [-VMReplication] <VMReplication[]> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Import-VMInitialReplication [-Path] <String> [-AsJob] [-PassThru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-VMInitialReplication** cmdlet imports initial replication files on a Replica server.
It completes the initial replication of a virtual machine when external is used as the source of the files for initial replication.

## EXAMPLES

### Example 1
```
PS C:\>Import-VMInitialReplication VM01 d:\VMImportLocation\VM01
```

This example imports the initial replication files for a virtual machine named VM01 from location d:\VMImportLocation\VM01.

### Example 2
```
PS C:\>Get-VMReplication | ForEach-Object {$path = "D:\OOBLoc\" + $_.VMName + "_" + $_.VMID; if (Test-Path $path -PathType Container) {Import-VMInitialReplication $_ $path}}
```

This example imports the initial replication files for a set of virtual machines using files located in D:\OOBLoc\

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

### -ComputerName
Specifies one or more Hyper-V hosts on which initial replication files are to be imported.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that an object is to be passed through to the pipeline representing the virtual machine for which initial replication files are to be imported.

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

### -Path
Specifies the path of the initial replication files to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IRLoc

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which the initial replication files are to be imported.

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

### -VMName
Specifies the name of the virtual machine for which the initial replication files are to be imported.

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

### -VMReplication
Specifies the virtual machine replication object for which initial replication files are to be imported.

```yaml
Type: VMReplication[]
Parameter Sets: VMReplication
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

