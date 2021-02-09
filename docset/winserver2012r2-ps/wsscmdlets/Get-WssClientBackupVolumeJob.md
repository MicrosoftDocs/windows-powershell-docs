---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssClientBackupVolumeJob
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4F453538-A753-4F08-BCB7-176993E618DF
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssClientBackupVolumeJob

## SYNOPSIS
Gets backup information for a backup volume job.

## SYNTAX

### ByName (Default)
```
Get-WssClientBackupVolumeJob [-BackupIndex] <Int32> [-ComputerName] <String> [<CommonParameters>]
```

### BySid
```
Get-WssClientBackupVolumeJob [-BackupIndex] <Int32> [-ComputerSid] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBackupVolumeJob** cmdlet gets backup information for a backup volume job.
Specify a computer by name or security identifier (SID).
Specify a job by using its index.

## EXAMPLES

### Example 1: Get backup volume job information
```
PS C:\> Get-WssClientBackupVolumeJob -ComputerName "Workstation073" -BackupIndex 1
```

This command gets information for a backup volume job for the computer named Workstation073.
The command specifies the backup index of the job.

## PARAMETERS

### -BackupIndex
Specifies the index for a backup volume job.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.VolumeJobInfo
This cmdlet generates volume job information.

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

