---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B16B8D37-9AF7-4F9C-B31E-F29155E2090F
manager: dansimp
---

# Remove-WBPolicy

## SYNOPSIS
Removes the backup policy.

## SYNTAX

```
Remove-WBPolicy [[-Policy] <WBPolicy>] [-All] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-WBPolicy** cmdlet removes the **WBPolicy** object.
This cmdlet stops scheduled daily backups from running.
If the backup storage location is a disk, the cmdlet frees the disk.
If the system does not have a scheduled backup, the cmdlet does not do anything.

To use this or any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove all scheduled backups
```
PS C:\> Remove-WBPolicy -All -Force
```

This command removes the currently set **WBPolicy** object and disables all scheduled backups on the system.
The command also uses the **Force** parameter to suppress the confirmation message.

### Example 2: Remove a specified backup policy
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Remove-WBPolicy -Policy $Policy
```

This command store the result of the Get-WBPolicy cmdlet in the variable named **$Policy**, then removes the **WBPolicy** object, which disables all scheduled backups on the system.

## PARAMETERS

### -All
Indicates that this cmdlet removes the **WBPolicy** object that is set in the system.

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

### -Force
Removes a policy without prompting you for confirmation.
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
Specifies the backup policy object to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: False
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
This cmdlet specifies the **WBPolicy** object to remove.

## OUTPUTS

### None
None

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that is set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the **Editable** parameter. The New-WBPolicy cmdlet creates a **WBPolicy** object that is already in edit mode.

  

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Set-WBPolicy](./Set-WBPolicy.md)

