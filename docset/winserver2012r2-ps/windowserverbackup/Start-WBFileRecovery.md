---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
online version: 
schema: 2.0.0
title: Start-WBFileRecovery
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: BAE102D6-B4DD-4818-81DA-92538547B1CD
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Start-WBFileRecovery

## SYNOPSIS
Starts a file recovery operation.

## SYNTAX

```
Start-WBFileRecovery [-BackupSet] <WBBackupSet> [-SourcePath] <String> [[-TargetPath] <String>]
 [[-Option] <WBFileRecoveryOptions>] [-Recursive] [-NoRestoreAcl] [-Async] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WBFileRecovery** cmdlet starts a file recovery operation.
For file recovery, you must specify the backup set from which to recover the file, along with the file that you want to recover.

To browse the volumes in backup, use the Get-WBBackupVolumeBrowsePath cmdlet.

## EXAMPLES

### Example 1 :Recover files to their original location
```
PS C:\> Start-WBFileRecovery -BackupSet $Backup -FilePathToRecover C:\Dir1 -Recursive -FileRecoveryOption CreateCopyIfExists -Force
Recovering files from C:\Dir1 :
Completed.
```

This command recovers the file at the path "C:\Dir1" from the backup set named **$Backup** and restores it to its original location.
Because the command includes the **Force** parameter, the backup proceeds without confirmation prompts.

### Example 2: Recover files to a new location
```
PS C:\>Get-WBBackupVolumeBrowsePath -BackupSet $Backup -VolumeInBackup $Backup.Volume[0]
\\Server01\WsbMountedVolumes\WsbMountedVolumeFile46_6fc68703-1c22-11e1-89cd-806e6f6e6963\ PS C:\>dir \\Server01\WsbMountedVolumes\WsbMountedVolumeFile46_6fc68703-1c22-11e1-89cd-806e6f6e6963\dir1\File1.txt
Directory: \\Server01\WsbMountedVolumes\WsbMountedVolumeFile46_6fc68703-1c22-11e1-89cd-806e6f6e6963\dir1
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        12/13/2011   2:35 PM          0 File1.txt PS C:\>Start-WBFileRecovery -BackupSet $Backup -FilePathToRecover \\Server01\WsbMountedVolumes\WsbMountedVolumeFile46_6fc68703-1c22-11e1-89cd-806e6f6e6963\Dir1\File1.txt -RecoveryTarget F:\Dir1
Warning
Start recovery of files from C:\Dir1\File1.txt to F:\Fir1 ?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Recovering files from C:\Dir1\File1.txt :
Completed.
```

This example recovers the file named C:\Dir1\File1.txt to the alternate location F:\Dir1.

The first command uses the Get-WBBackupVolumeBrowsePath cmdlet to get the volume browse path for the file that you recover.
The first element of the Volume array within the backup set stored in the variable named **$Backup** specifies the volume from which to obtain the backup files.

The second command checks the path that you obtained from the first command for a file named "File1.txt".

The third command restores the file named "File1.txt" to the path "F:\Dir1".

## PARAMETERS

### -Async
Indicates that Windows PowerShell® returns immediately after it starts the backup and does not display status messages.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupSet
Specifies a backup set object that contains the backup set from which you recover files.

```yaml
Type: WBBackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet starts the recovery operation without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -NoRestoreAcl
If specified, then security attributes for the files are not restored after recovery.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Option
Specifies an object that contains file recovery options.
The options specify the action to take when a file that you recover already exists in the same location.
The acceptable values for this parameter are:

-- **SkipIfExists**: Causes Windows Server Backup to skip the existing file and continue with recovery of the next file.
-- **CreateCopyIfExists**: Causes Windows Server Backup to create a copy of the existing file and not overwrite it.
-- **OverwriteIfExists**: Causes Windows Server Backup to overwrite the existing file with the file from the backup.

If you do not specify this parameter, the cmdlet uses the **CreateCopyIfExists** option by default.

```yaml
Type: WBFileRecoveryOptions
Parameter Sets: (All)
Aliases: 
Accepted values: Default, SkipIfExists, CreateCopyIfExists, OverwriteIfExists

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recursive
Indicates that Windows Server Backup recovers the files from the folders that you specify along with files in folders that are subordinate to those folders.
By default, the backup operation recovers only files that reside directly under the specified folders.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePath
Specifies the file path that you recover from the backup.
You can prefix the file path with a volume browse path that you get from the Get-WBBackupVolumeBrowsePath cmdlet.

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

### -TargetPath
Specifies the location where recovered files reside after the recovery.
If you do not specify this parameter, the backup operation recovers files to their original locations.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBBackupSet, WBFileRecoveryOptions
The file recovery process specifies a backup set object that contains the backup set from which you recover files.
The recovery process uses file recovery options when you recover files to their original locations and the file that you recover is already present in the original location.

## OUTPUTS

### System.String
If you do not specify the **Async** parameter, the recovery operation displays status messages at periodic intervals until the recovery is complete.
While the recovery operation runs you can use the Get-WBJob cmdlet to get the status of the operation.
After the operation is complete, you can use the `Get-WBJob -Previous 1` command to get the completed recovery status.

## NOTES

## RELATED LINKS

[Get-WBBackupVolumeBrowsePath](./Get-WBBackupVolumeBrowsePath.md)

