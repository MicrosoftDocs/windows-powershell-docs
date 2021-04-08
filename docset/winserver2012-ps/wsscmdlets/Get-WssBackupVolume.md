---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssbackupvolume?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupVolume

## SYNOPSIS
Gets backup volumes from a server, from a scheduled backup policy, or from existing backups.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WssBackupVolume [-AllVolumes]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WssBackupVolume [-BackupPolicy] <ScheduledBackupPolicy>
```

### UNNAMED_PARAMETER_SET_3
```
Get-WssBackupVolume [-CriticalVolumes]
```

### UNNAMED_PARAMETER_SET_4
```
Get-WssBackupVolume [-VolumeData] <ICollection<MountVhdData>>
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupPolicy
Specifies a scheduled backup policy.
The cmdlet gets all backup volumes from this scheduled backup policy.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CriticalVolumes
Indicates that the cmdlet gets all critical volumes from a server.
Critical volumes include the operating system volume and the Active Directory (AD) volume.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeData
Specifies a virtual hard disk (VHD) from which to retrieve the volumes.

```yaml
Type: ICollection<MountVhdData>
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupVolume](./Add-WssBackupVolume.md)

[Remove-WssBackupVolume](./Remove-WssBackupVolume.md)

