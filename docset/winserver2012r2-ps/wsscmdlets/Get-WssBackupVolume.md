---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupVolume
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 52E2B0C7-6155-4C5C-A6BA-383866CAB770
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Get-WssBackupVolume

## SYNOPSIS
Gets backup volumes from a server, from a scheduled backup policy, or from existing backups.

## SYNTAX

### Policy
```
Get-WssBackupVolume [-BackupPolicy] <ScheduledBackupPolicy> [<CommonParameters>]
```

### CriticalVolumes
```
Get-WssBackupVolume [-CriticalVolumes] [<CommonParameters>]
```

### AllVolumes
```
Get-WssBackupVolume [-AllVolumes] [<CommonParameters>]
```

### FullVolumesOnBackupSet
```
Get-WssBackupVolume
 [-VolumeData] <System.Collections.Generic.ICollection`1[Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.MountVhdData]>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupVolume** cmdlet gets backup volumes from a server, from a scheduled backup policy, or from an existing backup.

## EXAMPLES

### Example 1: Get critical volumes from a backup
```
PS C:\> Get-WssBackupVolume -CriticalVolumes
```

This command gets critical volumes from the server.

## PARAMETERS

### -AllVolumes
Indicates that the cmdlet gets all  backup volumes from a server.

```yaml
Type: SwitchParameter
Parameter Sets: AllVolumes
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupPolicy
Specifies a scheduled backup policy.
The cmdlet gets all backup volumes from this scheduled backup policy.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: Policy
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CriticalVolumes
Indicates that the cmdlet gets all critical volumes from a server.
Critical volumes include the operating system volume and the Active Directory (AD) volume.

```yaml
Type: SwitchParameter
Parameter Sets: CriticalVolumes
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeData
Specifies a virtual hard disk (VHD) from which to retrieve the volumes.

```yaml
Type: System.Collections.Generic.ICollection`1[Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.MountVhdData]
Parameter Sets: FullVolumesOnBackupSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.string

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.ClientVolumeInfo
This cmdlet returns backup volumes.

## NOTES

## RELATED LINKS

[Add-WssBackupVolume](./Add-WssBackupVolume.md)

[Remove-WssBackupVolume](./Remove-WssBackupVolume.md)

