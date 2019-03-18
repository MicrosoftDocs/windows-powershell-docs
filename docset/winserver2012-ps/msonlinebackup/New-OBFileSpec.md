---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 3F7C69FB-D90F-478D-AC68-C7952F4907EE
---

# New-OBFileSpec

## SYNOPSIS
Creates a new OBFileSpec object based on the parameters that are specified.

## SYNTAX

```
New-OBFileSpec [-FileSpec] <String[]> [-NonRecursive] [-Exclude]
```

## DESCRIPTION
The **New-OBFileSpec** cmdlet creates a new OBFileSpec object based on the parameters that are specified.
The OBFileSpec object defines what items will be included or excluded from backups.

Multiple files, folders, or volumes can be included or excluded.
Volume paths can be specified using volume drive letters, volume mount points, or GUID-based volume names.
If a GUID-based volume name is specified, it should be terminated with a backslash (`\\`).
The wildcard character (`*`) can be used in the file name when specifying a path to a file or when specifying a file type to include or exclude.

The items in the OBFileSpec object can be specified to be either recursive (include the item and everything subordinate to the item in the file structure) or non-recursive (include only the item).

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-OBFileSpec -FileSpec C:\testdata -NonRecursive
```

This example creates a new file specification for protection.

## PARAMETERS

### -Exclude
Specifies the list of items that are to excluded from the OBFileSpec object.
This parameter can include file paths and volumes (such as `C:`) or file specifications (such as `C:\dir1\*.*`).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSpec
Specifies the list of items for the OBFileSpec object.
This parameter can include file paths and volumes (such as `C:`) or file specifications (such as `C:\dir1\*.*`).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NonRecursive
Specifies that the items in the OBFileSpec object should be non-recursive, and only include the specified items.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBFileSpec
This cmdlet displays the OBFileSpec object which describes a file specification.
This can be added to the OBPolicy object as a source for backup.

## NOTES

## RELATED LINKS

[Add-OBFileSpec](./Add-OBFileSpec.md)

[Get-OBFileSpec](./Get-OBFileSpec.md)

[Get-OBPolicy](./Get-OBPolicy.md)

[New-OBRetentionPolicy](./New-OBRetentionPolicy.md)

[New-OBSchedule](./New-OBSchedule.md)

[Remove-OBFileSpec](./Remove-OBFileSpec.md)

[Remove-OBPolicy](./Remove-OBPolicy.md)

[Set-OBPolicy](./Set-OBPolicy.md)

[Set-OBRetentionPolicy](./Set-OBRetentionPolicy.md)

[Set-OBSchedule](./Set-OBSchedule.md)

