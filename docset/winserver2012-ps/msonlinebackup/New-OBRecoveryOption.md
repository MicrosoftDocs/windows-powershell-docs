---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 76561CB9-A585-4301-A70B-86B148473492
manager: dansimp
---

# New-OBRecoveryOption

## SYNOPSIS
Specifies the recovery options that will apply to all the recoverable items during recovery.

## SYNTAX

```
New-OBRecoveryOption [[-DestinationPath] <String>] [[-OverwriteType] <String>] [-SkipRestoreSecurity]
```

## DESCRIPTION
The **New-OBRecoveryOption** specifies the recovery options that will apply to all the recoverable items during recovery.
These include the Destination Path, Overwrite flag (for use in case if the object already exists), and Security settings for the object

If no Recovery Option is specified, the following default options will be used during recovery. 
1) Restore to original location. 
2) Create copies in case of conflict. 
3) Restore ACLs of the files.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-OBRecoveryOption -DestinationPath C:\temp -OverwriteType Overwrite -SkipRestoreSecurity
```

This example creates a new recovery option.

## PARAMETERS

### -DestinationPath
Specifies the location to recover.
This parameter is optional.

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

### -OverwriteType
Specifies whether to overwrite the existing files at the destination path.
The following three values are supported for this parameter - "CreateCopy", "Skip" and "Overwrite".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: CreateCopy
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipRestoreSecurity
Specifies whether to restore the access control lists (ACLs) of the files being recovered or to allow them to inherit the default ACLs of the restore location.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBRecoveryOption

## NOTES

## RELATED LINKS

[New-OBPagingContext](./New-OBPagingContext.md)

[New-OBRecoverableItem](./New-OBRecoverableItem.md)

[Start-OBRecovery](./Start-OBRecovery.md)
