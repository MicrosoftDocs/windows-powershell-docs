---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 2FC33236-9345-4F12-B713-A5908818D49D
manager: dansimp
---

# Set-OBRetentionPolicy

## SYNOPSIS
Sets the retention policy for the backup policy (OBPolicy object).

## SYNTAX

```
Set-OBRetentionPolicy [-Policy] <CBPolicy> [-RetentionPolicy] <CBRetentionPolicy> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-OBRetentionPolicy** cmdlet sets the retention policy for the backup policy (OBPolicy object).
The allowed retention days for the OBRetentionPolicy object are `7`, `15`,or `30`.

This cmdlet supports WhatIf and Confirm parameters with a medium impact.
The medium impact signifies that the cmdlet will not prompt the user for confirmation by default.
The WhatIf parameter gives a verbose description of what the cmdlet does without performing any operation.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using -Confirm:$FALSE will override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$newpo = New-OBPolicy

PS C:\>New-OBRetentionPolicy | Set-OBRetentionPolicy -Policy $newpo
```

This example sets up and updates a new retention policy.

## PARAMETERS

### -Policy
Specifies the policy related to backup.

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

### -RetentionPolicy
Specifies the retention policy to be used for backup.

```yaml
Type: CBRetentionPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

### Microsoft.Internal.CloudBackup.Commands.OBRetentionPolicy

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBRetentionPolicy

## NOTES

## RELATED LINKS

[New-OBPolicy](./New-OBPolicy.md)

[New-OBRetentionPolicy](./New-OBRetentionPolicy.md)

