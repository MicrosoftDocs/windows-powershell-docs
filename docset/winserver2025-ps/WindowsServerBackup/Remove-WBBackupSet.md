---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbbackupset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBBackupSet
---

# Remove-WBBackupSet

## SYNOPSIS
Removes backups from a target catalog, a system catalog, or both.

## SYNTAX

### Default (Default)
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [[-MachineName] <String>] [-Force] [<CommonParameters>]
```

### WBBackupTarget
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [-BackupTarget] <WBBackupTarget> [[-MachineName] <String>] [-Force] [<CommonParameters>]
```

### VolumePath
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [-VolumePath] <String> [[-MachineName] <String>] [-Force] [<CommonParameters>]
```

### NetworkWithPSCred
```
Remove-WBBackupSet [[-BackupSet] <WBBackupSet[]>] [[-KeepVersions] <Int32>] [-DeleteOldest]
 [-NetworkPath] <String> [[-Credential] <PSCredential>] [-NonInheritAcl] [[-MachineName] <String>] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBBackupSet** cmdlet removes a set of backups from a target catalog, a system catalog, or both.

## EXAMPLES

### Example 1: Remove oldest backup set
```
PS C:\> $Ret = Remove-WBBackupSet -DeleteOldest -BackupTarget $WB_BackupTarget -MachineName $MachineName -Force
```

This command deletes the oldest backup of the computer that has its name in the $MachineName variable from the backup target and stores the result in the variable named $Ret.
Because the command includes the *Force* parameter, it does not ask for confirmation of the deletion.

## PARAMETERS

### -BackupSet
Specifies an array of backup set objects that determine which backup or which backup sets that this cmdlet removes.
You can specify one backup or an array of backup sets.

```yaml
Type: WBBackupSet[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupTarget
Specifies a backup target object that indicates the storage location with the backups that you want to remove.

Use this parameter to delete backups from computers other than the local computer.
The cmdlet deletes the backup sets from the catalog on the computer that you specify in this parameter and from the system catalog of the local computer.
These locations can be locally attached disk drives or remote shared folders.

```yaml
Type: WBBackupTarget
Parameter Sets: WBBackupTarget
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object that contains the username and password for a user account that has access permissions for the location that stores backups.

To obtain a credential object, use the Get-Credential cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: NetworkWithPSCred
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DeleteOldest
Indicates that the cmdlet removes the oldest backup in the set.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepVersions
Specifies the number of the most recent backups to keep on the backup target.
The cmdlet removes backups over this number from the target.

If you specify this parameter along with the *BackupTarget* and *MachineName* parameters, the cmdlet examines the target location on the specified computer for backups to remove.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Specifies the name of the computer for which this cmdlet removes backups.

Use this parameter when you specify the *BackupTarget* parameter or when multiple computers store backups in the same location.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkPath
Specifies the path to the remote shared folder from which the cmdlet removes backups.

```yaml
Type: String
Parameter Sets: NetworkWithPSCred
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonInheritAcl
Do not use.
This parameter is not implemented in this version of the module.

```yaml
Type: SwitchParameter
Parameter Sets: NetworkWithPSCred
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumePath
Specifies the drive letter of the volume where the cmdlet stores backups.

```yaml
Type: String
Parameter Sets: VolumePath
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBBackupSet[]

### System.Management.Automation.PSCredential

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WBBackupSet](./Get-WBBackupSet.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

