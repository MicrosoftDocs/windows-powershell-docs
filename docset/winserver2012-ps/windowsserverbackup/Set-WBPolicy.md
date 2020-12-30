---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 1213FFEC-6B21-4134-9997-8A9C3EADB9EE
manager: dansimp
---

# Set-WBPolicy

## SYNOPSIS
Sets the backup policy for scheduled backups.

## SYNTAX

```
Set-WBPolicy [-Policy] <WBPolicy> [-AllowDeleteOldBackups] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WBPolicy** cmdlet sets a **WBPolicy** object as the backup policy for scheduled backups.

To use this or any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Set a backup policy
```
The first command creates a backup policy object and stores it in the **$Policy** variable.
PS C:\> $Policy = New-WBPolicy

The second command creates a file specification object and stores the result in the **$FileSpec** variable. A file specification determines what items to include or exclude from backups.
PS C:\>$FileSpec = New-WBFileSpec -FileSpec C:\dir1

The third command adds a Windows Backup file specification to the backup policy.
PS C:\>Add-WBFileSpec -Policy $Policy -FileSpec $FileSpec

The fourth command adds bare metal recovery to the policy.
PS C:\>Add-WBBareMetalRecovery $Policy

The fifth command gets the Windows Backup disk configuration. This cmdlet gets the list of internal and external disks available for the local computer and stores the resulting list in the **$Disks** variable.
PS C:\>$Disks = Get-WBDisk

The sixth command creates a backup target object and stores it in the **$BackupLocation** variable.
PS C:\>$BackupLocation = New-WBBackupTarget -Disk $Disks[2]

The seventh command adds a backup target. The **$BackupLocation** variable specifies the backup locations in the policy.
PS C:\>Add-WBBackupTarget -Policy $Policy -Target $BackupLocation 

The eighth command sets the backup schedule in the policy. The cmdlet sets the times to create daily backups.
PS C:\>Set-WBSchedule -Policy $Policy 09:00

The ninth command sets the backup policy object for the computer.
PS C:\>Set-WBPolicy -Policy $Policy
```

This example sets a new backup policy.

### Example 2: Set backup policy by using a remote shared file
```
The first command gets the backup policy object and stores it in the **$Policy** variable.
PS C:\>$Policy = Get-WBPolicy -Editable

The second command creates a backup target object and stores it in the **$BackupLocation** variable. When you are prompted, specify the credentials to access the remote shared folder and acknowledge the warning about choosing a remote shared folder as a backup storage location.
PS C:\>$BackupLocation = New-WBBackupTarget -NetworkPath \\ContosoSrv\ContosoShared

The third command adds a backup target to the policy. The target is the **$BackupLocation** variable.
PS C:\>Add-WBBackupTarget -Policy $policy -Target $BackupLocation 

The fourth command sets backup policy object from the changes to the **$Policy** variable.
PS C:\>Set-WBPolicy -Policy $Policy
```

This example modifies the backup policy for the set **WBPolicy** object and changes the backup location to a remote file share.

## PARAMETERS

### -AllowDeleteOldBackups
Indicates whether new backups can overwrite older backups.

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
Sets the policy without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -Policy
Specifies a **WBPolicy** object that contains that contains a backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### WBPolicy
The **Set-WBPolicy** cmdlet sets a **WBPolicy** object as the current backup policy to use for scheduled backups.

## OUTPUTS

### None
None

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that is set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the **Editable** parameter. The New-WBPolicy cmdlet creates a **WBPolicy** object in edit mode.

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBPolicy](./Remove-WBPolicy.md)

