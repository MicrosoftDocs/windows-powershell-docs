---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 5828A2EA-5947-40E5-AB51-33BD36F8CC29
---

# Remove-OBFileSpec

## SYNOPSIS
Removes the list of items to include or exclude from a backup, as specified by the OBFileSpec object, from a backup policy (OBPolicy) object.

## SYNTAX

```
Remove-OBFileSpec [-Policy] <CBPolicy> [-FileSpec] <CBFileSpec[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Remove-OBFileSpec cmdlet removes the list of items to include or exclude from a backup, as specified by the OBFileSpec object, from a backup policy (OBPolicy object).
After making changes to the policy object, Set-OBPolicy must be called to set this policy as the current one.

This cmdlet supports WhatIf and Confirm parameters with a medium impact.
The medium impact signifies that the cmdlet will not prompt the user by default.
The WhatIf parameter gives a verbose description of what the cmdlet does.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using -Confirm:$FALSE will override the prompt.

.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$policy = Get-OBPolicy



PS C:\>Get-OBFileSpec -Policy $policy | Remove-OBFileSpec -Policy $policy
```

This example removes an existing file specification.

## PARAMETERS

### -FileSpec
Specifies the items to remove from the OBPolicy object.

```yaml
Type: CBFileSpec[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Policy
Specifies the policy from which the file specification should be deleted.

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

[Get-OBFileSpec](./Get-OBFileSpec.md)

[New-OBPolicy](./New-OBPolicy.md)

