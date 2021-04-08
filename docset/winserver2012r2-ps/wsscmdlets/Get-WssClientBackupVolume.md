---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssclientbackupvolume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssClientBackupVolume
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

