---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/restore-dfsrpreservedfiles?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DfsrPreservedFiles
---

# Restore-DfsrPreservedFiles

## SYNOPSIS
Restores files and folders that DFS Replication previously preserved.

## SYNTAX

### RestorePath (Default)
```
Restore-DfsrPreservedFiles [-Path] <String> [-RestoreToPath] <String> [-RestoreAllVersions] [-CopyFiles]
 [-AllowClobber] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RestoreOrigin
```
Restore-DfsrPreservedFiles [-Path] <String> [-RestoreToOrigin] [-RestoreAllVersions] [-CopyFiles]
 [-AllowClobber] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-DfsrPreservedFiles** cmdlet restores preserved files and folders.
The Distributed File System (DFS) Replication service preserves the following kinds of files and folders:

- Conflicted.
If users make changes to the same file on multiple servers before replication converges, a file might conflict with the current version.
DFS Replication preserves previous conflicting versions of the file.
- Deleted.
When a member computer deletes a replicated file, other members also remove that file.
Depending on membership settings, computers can preserve deleted files.
To modify whether a member computer preserves deleted files, use the **Set-DfsrMembership** cmdlet.
- Preexisting.
If DFS Replication overwrites files during its initial synchronization, DFS Replication preserves those files.

For all three types, DFS Replication moves the files to \<replicated folder\>\DfsrPrivate\ConflictAndDeleted or \<replicated folder\>\DfsrPrivate\Preexisting.
DFS Replication records these files in a manifest, either ConflictAndDeletedManifest.xml or PreExistingManifest.xml, as appropriate.
Specify the ConflictAndDeletedManifest.xml manifest to restore conflicted and deleted files and folders.
Specify the PreExistingManifest.xml manifest to restore preexisting files and folders.
You can use the **Get-DfsrPreservedFiles** cmdlet to view preserved files and folders.

CAUTION By default, this cmdlet moves all files and removes any existing preserved files, including older versions of files.
Consider backing up the ConflictsAndDeleted and Preexisting folder before you use this cmdlet.

## EXAMPLES

### Example 1: Restore preexisting files to their original locations
```
PS C:\> Restore-DfsrPreservedFiles -Path "C:\RF01\DfsrPrivate\PreExistingManifest.xml" -RestoreToOrigin
```

This command restores preexisting files and folders in the replicated folder C:\RF01 to their original locations.
The command does not specify the *CopyFiles* parameter.
Therefore, it moves the files and leaves the Preexisting folder empty.

### Example 2: Restore copies of preexisting files to a different location
```
PS C:\> Restore-DfsrPreservedFiles -Path "C:\RF01\DfsrPrivate\PreExistingManifest.xml" -RestoreToPath "C:\DFSRTest" -CopyFiles -AllowClobber -Verbose
VERBOSE: Loading Preserved file Manifest C:\rf01\DfsrPrivate\PreExistingManifest.xml
VERBOSE: Restoring Preserved Files from manifest C:\rf01\DfsrPrivate\PreExistingManifest.xml
```

This command restores copies of preexisting files and folders in the replicated folder C:\RF01 to the location C:\DFSRTest.
The command specifies the location by using the *RestoreToPath* parameter.
The command uses the *AllowClobber* parameter.
Therefore, it overwrites existing files that have the same names in the specified location.
The command uses the *Verbose* parameter to display information in the console.

### Example 3: Restore conflicted and deleted files to a different location
```
PS C:\> Restore-DfsrPreservedFiles -Path "C:\RF01\DfsrPrivate\ConflictAndDeletedManifest.xml" -RestoreToPath "C:\DFSRRestore" -RestoreAllVersions -Force
PS C:\> Get-ChildItem -Path "C:\DFSRRestore"
    Directory: C:\dfsrrestore

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---          4/5/2013   9:58 AM     848294 canary.bmp
-a---          4/5/2013   9:58 AM     848294 canary2013_04_05_17_00_00Z.bmp
-a---          4/5/2013   9:58 AM     848294 canary2013_04_05_17_17_37Z.bmp
-a---          4/5/2013   9:58 AM     848294 canary2013_04_05_17_17_47Z.bmp
```

This example restores multiple versions of conflicted and deleted files to a specified location.

The first command restores conflicted and deleted files and folders for the replicated folder C:\FR01 to the location C:\DFSRRestore.
The command restores all preserved versions of the files.
The command includes the *Force* parameter, and therefore, it does not prompt you for confirmation and overwrites any files in the destination.

The second command uses the **Get-ChildItem** cmdlet to display information about the restored files.
For more information, type `Get-Help Get-ChildItem`.
In this example, the first command restores multiple versions of the same file.

## PARAMETERS

### -AllowClobber
Indicates that the cmdlet overwrites files of the same name that currently exist in the destination.
If you do not specify this parameter, the cmdlet prompts you before overwriting existing files.

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

### -CopyFiles
Indicates that the cmdlet copies files instead of moving them.

If you do not specify this parameter, the cmdlet moves the preserved files but restores only the latest version of a file.
You will lose previous versions of conflicted or deleted files.
Preexisting files never have multiple versions.
To avoid losing previous versions, consider backing up the ConflictsAndDeleted folder.
As an alternative, specify the *RestoreAllVersions* parameter.

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
Forces the command to run without asking for user confirmation.

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

### -Path
Specifies the path of a manifest.
By default, the manifest files exist in the \<Replicated Folder\>\DfsrPrivate folder.
Specify ConflictAndDeletedManifest.xml to restore conflicted and deleted files.
Specify PreExistingManifest.xml to restore preexisting files.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RestoreAllVersions
Indicates that the cmdlet restores all versions of a file.
The cmdlet adds a time stamp to the file name.
This parameter affects only conflicted files or deleted files.
Preexisting files never have multiple versions.

If you do not specify this parameter, the cmdlet restores only the most recent version of the file.
If you do not specify this parameter and do not specify the *CopyFiles* parameter, the cmdlet restores the most recent version and removes all versions from the ConflictsAndDeleted folder.
Consider backing up the ConflictsAndDeleted folder before you use this cmdlet.

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

### -RestoreToOrigin
Indicates that the cmdlet restores all files and folders recorded in the ConflictAndDeletedManifest.xml manifest or the PreExistingManifest.xml manifest to their original locations.
To restore to a different location, specify a path by using the *RestoreToPath* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: RestoreOrigin
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreToPath
Specifies a location for files and folders recorded in the ConflictAndDeletedManifest.xml manifest or the PreExistingManifest.xml manifest.
To restore to the original locations, specify the *RestoreToOrigin* parameter.

```yaml
Type: String
Parameter Sets: RestorePath
Aliases:

Required: True
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DfsrPreservedFiles](./Get-DfsrPreservedFiles.md)

[Set-DfsrMembership](./Set-DfsrMembership.md)

