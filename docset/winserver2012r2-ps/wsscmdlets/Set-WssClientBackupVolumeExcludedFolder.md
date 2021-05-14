---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssclientbackupvolumeexcludedfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssClientBackupVolumeExcludedFolder
---

# Set-WssClientBackupVolumeExcludedFolder

## SYNOPSIS
Specifies folders to exclude from client backup on a computer.

## SYNTAX

### ByName (Default)
```
Set-WssClientBackupVolumeExcludedFolder
 [[-ExcludedFolders] <System.Collections.Generic.ICollection`1[System.String]>] [-Clear] [-VolumeGuid] <Guid>
 [-ComputerName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySid
```
Set-WssClientBackupVolumeExcludedFolder
 [[-ExcludedFolders] <System.Collections.Generic.ICollection`1[System.String]>] [-Clear] [-VolumeGuid] <Guid>
 [-ComputerSid] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssClientBackupVolumeExcludedFolder** cmdlet specifies folders to exclude from client backup on a computer.
Specify a computer by name or security identifier (SID).
Specify a volume by using its GUID.

If you use the **Clear** parameter, the cmdlet clears the list of excluded folders, so future backups do not exclude any folders.

## EXAMPLES

### Example 1: Exclude folders from backup for a volume
```
PS C:\> Set-WssClientBackupVolumeExcludedFolder -ComputerName "Workstation073" -VolumeGuid b6b093a2-1860-4172-a4a5-07ce2aebfa13 -ExcludedFolders (@("Temp\","Downloads\") -as [string[]])
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

### -ExcludedFolders
Specifies a collection of folder paths.
The volume containing the folders is specified by the -VolumeGuid parameter, so do not include the volume letter as part of the path.

```yaml
Type: System.Collections.Generic.ICollection`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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
Position: 3
Default value: None
Accept pipeline input: False
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

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

