---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 6B0CD195-2EB7-4A54-B356-590E6ECAF2FE
manager: dansimp
---

# Remove-OBPolicy

## SYNOPSIS
Removes or pauses the currently set backup policy (OBPolicy object).

## SYNTAX

```
Remove-OBPolicy [-Policy] <CBPolicy> [-DeleteBackup] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-OBPolicy** cmdlet removes or pauses the currently set backup policy (OBPolicy object). 
If the **DeleteBackup** parameter is specified, then any data backed up according to this policy on the mob_name_1 server is deleted and any existing schedule for backups is deleted as well. 
If the **DeleteBackup** parameter is not specified, the existing backups are retained in accordance with the retention policy in effect when the backup was created, and the existing schedule for backups is paused. 

This cmdlet supports the *WhatIf* and the *Confirm* parameters.
The cmdlet prompts the user for confirmation by default.
The *WhatIf* parameter gives a verbose description of what the cmdlet does without performing any operation.
The *Confirm* parameter specifies whether the cmdlet should prompt the user.
Specify -`Confirm:$FALSE`  to override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBPolicy | Remove-OBPolicy
```

This example deletes an existing policy.

## PARAMETERS

### -DeleteBackup
Specifies that all data backed up on the mob_name_1 server associated with this policy should be deleted immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies the policy to be removed.

```yaml
Type: CBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicy

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)
