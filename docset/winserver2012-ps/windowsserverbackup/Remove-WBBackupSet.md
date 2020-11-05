---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: E057BEDD-F281-4463-9E4A-29DA9D8E171C
manager: dansimp
---

# Remove-WBBackupSet

## SYNOPSIS
Deletes backups from a target catalog, a system catalog, or both.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [[-MachineName] <String>] [-Force]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [-BackupTarget] <WBBackupTarget> [[-MachineName] <String>] [-Force]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [-NetworkPath] <String> [[-Credential] <PSCredential>] [-NonInheritAcl] [[-MachineName] <String>] [-Force]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [-VolumePath] <String> [[-MachineName] <String>] [-Force]
```

## DESCRIPTION
The **Remove-WBBackupSet** cmdlet deletes a set of backups from a target catalog, a system catalog, or both.

## EXAMPLES

### Example 1: Remove oldest backup set
```
PS C:\> $Ret = Remove-WBBackupSet -DeleteOldest -BackupTarget $WB_BackupTarget -MachineName $MachineName -Force
```

This command deletes the oldest backup of the computer that has its name in the **$MachineName** variable from the backup target.
Because the command includes the **Force** parameter, it does not ask for confirmation of the deletion.

## PARAMETERS

### -BackupSet
Specifies an array of backup set objects that determine which backup or which backup sets to delete.
You can specify one backup or an array of backup sets.

```yaml
Type: WBBackupSet[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupTarget
Specifies a backup target object that indicates the storage location with the backups that you want to delete.

Use this parameter to delete backups from computers other than the local computer.
The cmdlet deletes the backup sets from the catalog on the computer that you specify in this parameter and from the system catalog of the local computer.
These locations can be locally attached disk drives or remote shared folders.

```yaml
Type: WBBackupTarget
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object that contains the username and password for a user account that has access permissions for the location that stores backups.

```yaml
Type: PSCredential
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DeleteOldest
Indicates that the cmdlet deletes the oldest backup in the set.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet removes the backup set without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepVersions
Specifies the number of the most recent backups to keep on the backup target.
The cmdlet deletes backups over this number from the target.

If you specify this parameter along with the **BackupTarget** and **MachineName** parameters, the cmdlet examines the target location on the specified computer for backups to remove.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Specifies the name of the computer for which you want to delete backups.

Use this parameter when you specify the **BackupTarget** parameter or when multiple computers store backups in the same location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkPath
Specifies the path to the remote shared folder from which the cmdlet deletes backups.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonInheritAcl
Do not use.
This parameter is not implemented in this version of the module.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumePath
Specifies the drive letter of the volume where the cmdlet stores backups.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Windows.ServerBackup.Commands.WBBackupSet,System.Int32,System.Management.Automation.SwitchParameter, Windows.ServerBackup.Commands.WBBackupTarget, System.String, System.Management.Automation.PSCredential

## OUTPUTS

### Windows.ServerBackup.Commands.WBBackupSet

## NOTES

## RELATED LINKS



[Get-WBBackupSet](./Get-WBBackupSet.md)

