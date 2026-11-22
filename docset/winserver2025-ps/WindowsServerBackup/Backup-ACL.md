---
description: The Backup-Acl cmdlet backs up the security descriptor of a specified item, such as a file or a registry key.
external help file: wsbcmdlet.dll-help.xml
Module Name: WindowsServerBackup
ms.date: 09/10/2021
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/backup-acl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Backup-ACL
---

# Backup-ACL

## SYNOPSIS
Backs up the security descriptor of an item.

## SYNTAX

```
Backup-ACL [-Path] <String> [-DestinationPath] <String> [-LogPath] <String> [[-ScheduleTrigger] <Object>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Backup-Acl** cmdlet backs up the security descriptor of a specified item, such as a file or a registry key.

To back up an ACL, specify the **Path** parameter to identify the item. Use the **DestinationPath** parameter to specify the location for the backup.

## EXAMPLES

### Example 1: Back up the ACL for a file
```powershell
Backup-ACL -Path "C:\file01.txt" -DestinationPath "C:\AclBackups\file01.xml" -LogPath "C:\AclBackupLogs\"
```

This command backs up the ACL for the specified file.
The command also specifies the location for the backup and the log.

### Example 2: Back up on a schedule
```powershell
$TaskTrigger = New-ScheduledTaskTrigger -Daily -At 6am
Backup-ACL -Path "C:\file02.txt" -DestinationPath "C:\AclBackups\" -LogPath "C:\AclBackups\" -ScheduleTrigger $TaskTrigger
```

This example backs up the ACL on a regular schedule.

The first command creates a scheduled task trigger by using the **New-ScheduledTaskTrigger** cmdlet and stores it in the `$TaskTrigger` variable.

The second command backs up the ACL according to the schedule object, in this case, daily at 6:00 AM.

## PARAMETERS

### -DestinationPath
Specifies a full path to store the permission backup.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogPath
Specifies a full path for the log file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the full path of the object for which the cmdlet backs up permissions.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ScheduleTrigger
Specifies a **ScheduleTrigger** object.
A trigger creates pipeline runs periodically, on schedule.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Object

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-ACL](/powershell/module/microsoft.powershell.security/get-acl)

[New-ScheduledTaskTrigger](../scheduledtasks/New-ScheduledTaskTrigger.md)

[Restore-ACL](Restore-ACL.md)
