---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B88533EF-4FCA-4EBE-98E9-C05D8AA2235F
manager: dansimp
---

# New-WBFileSpec

## SYNOPSIS
Creates a backup file specification.

## SYNTAX

```
New-WBFileSpec [-FileSpec] <String[]> [-NonRecursive] [-Exclude]
```

## DESCRIPTION
The **New-WBFileSpec** cmdlet creates a **WBFileSpec** object that contains a backup file specification.
A **WBFileSpec** object defines the items the items that a backup includes or excludes.
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
PS C:\> $Filespec = New-WBFileSpec -FileSpec C:\Sample\1.jpg

The WBFileSpec object that specifies the file C:\Sample\1.jpg for backup.
```

This command creates a file specification and adds the file named "C:\Sample\1.jpg" to it.

### Example 2: Add a volume recursively to a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec C:\Sample

The WBFileSpec object that specifies the folder C:\Sample for backup.
```

This command creates a file specification and adds the contents of the "C:\Sample" folder to it.
Because the cmdlet does not include the **NonRecursive** parameter, the backup includes the contents of this folder and its subfolders.

### Example 3: Add a volume nonrecursively to a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec C:\Sample -NonRecursive

The WBFileSpec object that specifies the folder C:\sample for backup non-recursively.
```

This command creates a file specification and adds the contents of the "C:\Sample" folder to it.
Because the cmdlet includes the **NonRecursive** parameter, the backup includes the contents of this folder but not the contents of its subfolders.

### Example 4: Exclude files from a backup file specification
```
PS C:\> $Filespec = New-WBFileSpec -FileSpec C:\Sample\*.mp3 -Exclude

The WBFileSpec object that specifies the exclusion of*.mp3 files during backup under the path C:\Sample.
```

This command creates an exclusion file specification for MP3 files in the "C:\Sample" folder.
The backup excludes MP3 files in "C:\Sample" and its subfolders.

## PARAMETERS

### -Exclude
Indicates that the backup excludes the items in the **FileSpec** parameter from the backup.

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

### -FileSpec
Specifies a list of names of items to include in or exclude from the backup.
This parameter can include file paths and volumes (such as "C:\") or file specifications (such as "C:\dir1\*.*").

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Spec string, NonRecursive, Excluded flags
The New-WBFileSpec cmdlet uses **Spec**, **NonRecursive**, and **Excluded** parameters to create a list of items to include or exclude.
**Spec** accepts string objects.

## OUTPUTS

### WBFileSpec
The New-WBFileSpec cmdlet displays a **WBFileSpec** object, which describes a file specification.
You can add a **WBFileSpec** object to a **WBPolicy** object as a source for backup.

## NOTES

## RELATED LINKS

[Add-WBFileSpec](./Add-WBFileSpec.md)

[Get-WBFileSpec](./Get-WBFileSpec.md)

[Remove-WBFileSpec](./Remove-WBFileSpec.md)

