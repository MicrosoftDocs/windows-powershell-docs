---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 0B8B0A93-ED16-4E01-9140-5F8386D8803D
manager: dansimp
---

# Get-WBVssBackupOption

## SYNOPSIS
Retrieves a VSS setting from the backup policy.

## SYNTAX

```
Get-WBVssBackupOption [-Policy] <WBPolicy>
```

## DESCRIPTION
The **Get-WBVSSBackupOptions** cmdlet retrieves a setting that determines whether the backups created through the **WBPolicy** object are Volume Shadow Copy Service (VSS) copy backups or VSS full backups.
For more information about VSS copy backups and VSS full backups, or to change this setting, refer to the **Set-WBVSSBackupOptions** cmdlet.

To use Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the VSS setting from the backup policy
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Get-WBVssBackupOptions -Policy $Policy
```

This example gets the VSS setting, either VssCopyBackup or VssFullBackup.

The first command stores the result ofthe Get-WBPolicy cmdlet in the variable named $Policy.

The second command gets the VSS setting from the variable $Policy.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object to display.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### WBPolicy
The **Get-WBVssBackupOptions** cmdlet queries the **WBPolicy** object.

## OUTPUTS

### Microsoft.Windows.ServerBackup.Commands.VssBackupOptions
The **Get-WBVssBackupOptions** cmdlet returns either VssCopyBackup or VssFullBackup, depending on the option specified in the **WBPolicy** object.

## NOTES

## RELATED LINKS

[New-WBPolicy](./New-WBPolicy.md)

[Set-WBVssBackupOption](./Set-WBVssBackupOption.md)
