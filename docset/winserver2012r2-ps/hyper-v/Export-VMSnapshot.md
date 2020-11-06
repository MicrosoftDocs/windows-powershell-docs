---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Export-VMSnapshot
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
ms.assetid: 6B839212-BB3E-4321-92C1-A32FFC38FDFD
---

# Export-VMSnapshot

## SYNOPSIS
Exports a virtual machine checkpoint to disk.

## SYNTAX

### SnapshotName (Default)
```
Export-VMSnapshot [-ComputerName <String[]>] [-Name] <String[]> [-Path] <String> -VMName <String[]> [-AsJob]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SnapshotObject
```
Export-VMSnapshot [-VMSnapshot] <VMSnapshot[]> [-Path] <String> [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Export-VMSnapshot [-Name] <String[]> [-Path] <String> [-AsJob] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-VMSnapshot** cmdlet exports a virtual machine checkpoint to disk.

Note: In Windows Server 2012 R2, virtual machine snapshots were renamed to virtual machine checkpoints.
For clarity, this document will refer to virtual machine snapshots as checkpoints.

## EXAMPLES

### Example 1
```
PS C:\>Export-VMSnapshot -Name 'Base Image' -VMName TestVM -Path D:\
```

Exports checkpoint Base Image of virtual machine TestVM to D:\.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run a background job.

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
Specifies one or more Hyper-V hosts on which the virtual machine checkpoint is to be exported.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SnapshotName
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

### -Name
Specifies the name of the checkpoint to be exported.

```yaml
Type: String[]
Parameter Sets: SnapshotName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMSnapshot** object is to be passed through to the pipeline representing the checkpoint to be exported.

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
Specifies the path to the folder into which the checkpoint is to be exported.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine of which the checkpoint is to be exported.

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
Specifies the name of the virtual machine of which the checkpoint is to be exported.

```yaml
Type: String[]
Parameter Sets: SnapshotName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the checkpoint to be exported.

```yaml
Type: VMSnapshot[]
Parameter Sets: SnapshotObject
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
None by default; **Microsoft.HyperV.PowerShell.Snapshot** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

