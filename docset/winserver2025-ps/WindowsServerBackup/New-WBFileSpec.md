---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/new-wbfilespec?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WBFileSpec
---

# New-WBFileSpec

## SYNOPSIS
Creates a backup file specification.

## SYNTAX

```
New-WBFileSpec [-FileSpec] <String[]> [-NonRecursive] [-Exclude] [<CommonParameters>]
```

## DESCRIPTION
The **New-WBFileSpec** cmdlet creates a **WBFileSpec** object that contains a backup file specification.
A **WBFileSpec** object defines the items that a backup includes or excludes.
You can add a backup file specification to a **WBPolicy** object as a source for backup.

You can use this cmdlet to include multiple files, folders, or volumes.
Specify volume paths by using volume drive letters, volume mount points, or GUID-based volume names.
If you use a GUID-based volume name, ensure that it ends with a backslash (\\).
You can use wildcard characters (*) in file names to specify a path to a file or to specify a file type to include or exclude.

If you specify a path to exclude from the backup, that path must be part of an inclusion file specification in the policy.
Otherwise, the backup ignores the exclusion path.

## EXAMPLES

### Example 1: Add a file to a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec "C:\Sample\1.jpg"
```

This command creates a file specification and adds the file named C:\Sample\1.jpg to it.

### Example 2: Add a folder recursively to a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec "C:\Sample"
```

This command creates a file specification and adds the contents of the C:\Sample folder to it.
Because the cmdlet does not include the *NonRecursive* parameter, the backup includes the contents of this folder and its subfolders.

### Example 3: Add a folder nonrecursively to a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec "C:\Sample" -NonRecursive
```

This command creates a file specification and adds the contents of the C:\Sample folder to it.
Because the cmdlet includes the *NonRecursive* parameter, the backup includes the contents of this folder but not the contents of its subfolders.

### Example 4: Exclude files from a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec "C:\Sample\*.mp3" -Exclude
```

This command creates an exclusion file specification for MP3 files in the C:\Sample folder.
The backup excludes MP3 files in C:\Sample and its subfolders and stores it in the variable named $Filespec.

## PARAMETERS

### -Exclude
Indicates that the backup excludes the items in the *FileSpec* parameter from the backup.

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

### -FileSpec
Specifies a list of names of items to include in or exclude from the backup.
This parameter can include file paths and volumes (such as "C:\") or file specifications (such as "C:\dir1\*.*").

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonRecursive
Indicates that the backup includes only the items in the **WBFileSpec** object and not subordinate items.
If you do not include this option, the backup includes items recursively.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

This cmdlet returns a **WBFileSpec** object, which describes a file specification.
You can add a **WBFileSpec** object to a **WBPolicy** object as a source for backup.

## NOTES

## RELATED LINKS

[Add-WBFileSpec](./Add-WBFileSpec.md)

[Get-WBFileSpec](./Get-WBFileSpec.md)

[Remove-WBFileSpec](./Remove-WBFileSpec.md)

