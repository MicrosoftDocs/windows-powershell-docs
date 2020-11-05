---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B3A453AA-AB78-4DA7-9931-1436F854C5EC
manager: dansimp
---

# Set-WssClientBackupVolumeExcludedFolder

## SYNOPSIS
Specifies folders to exclude from client backup on a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-WssClientBackupVolumeExcludedFolder [-ComputerName] <String> [-VolumeGuid] <Guid>
 [[-ExcludedFolders] <ICollection<String>>] [-Clear] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-WssClientBackupVolumeExcludedFolder [-ComputerSid] <String> [-VolumeGuid] <Guid>
 [[-ExcludedFolders] <ICollection<String>>] [-Clear] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssClientBackupVolumeExcludedFolder** cmdlet specifies folders to exclude from client backup on a computer.
Specify a computer by name or security identifier (SID).
Specify a volume by using its GUID.

If you use the **Clear** parameter, the cmdlet clears the list of excluded folders, so future backups do not exclude any folders.

## EXAMPLES

### Example 1: Exclude folders from backup for a volume
```
PS C:\> Set-WssClientBackupVolumeExcludedFolder -ComputerName "Workstation073" -VolumeGuid b6b093a2-1860-4172-a4a5-07ce2aebfa13 -ExcludedFolders (@("C:\Temp","C:\Downloads") -as [string[]])
```

This command excludes folders for the specified volume for the computer named Workstation073.
The command accepts a collection of folders to exclude from backup.

## PARAMETERS

### -Clear
Indicates that the cmdlet clears the list of excluded folders.

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
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerSid
Specifies the SID of a computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludedFolders
Specifies a collection of folder paths.

```yaml
Type: ICollection<String>
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeGuid
Specifies the GUID of a volume.
To obtain a GUID, use the Get-WssClientBackupVolume cmdlet.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

