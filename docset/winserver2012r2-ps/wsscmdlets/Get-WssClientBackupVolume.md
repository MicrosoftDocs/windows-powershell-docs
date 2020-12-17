---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssClientBackupVolume
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 73476D36-C62C-484B-B674-9D549686C92C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssClientBackupVolume

## SYNOPSIS
Gets the volume configuration of a computer.

## SYNTAX

### ByName (Default)
```
Get-WssClientBackupVolume [-ComputerName] <String> [<CommonParameters>]
```

### BySid
```
Get-WssClientBackupVolume [-ComputerSid] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBackupVolume** cmdlet gets the volume configuration of a previously backed up computer.
Specify a computer by name or security identifier (SID).

## EXAMPLES

### Example 1: Get volume configuration for a client computer
```
PS C:\> Get-WssClientBackupVolume -ComputerName "Workstation073"
```

This command gets the volume configuration for a computer named Workstation073.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerSid
Specifies the SID of a computer.

```yaml
Type: String
Parameter Sets: BySid
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.ObjectModel.PCBackupClientVolume
This cmdlet generates a backup volume.

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolumeJob](./Get-WssClientBackupVolumeJob.md)

