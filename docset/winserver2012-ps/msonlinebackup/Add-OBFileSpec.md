---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: C9BAD40B-646F-4AFF-94A0-7D5F33CF2F57
manager: dansimp
---

# Add-OBFileSpec

## SYNOPSIS
Adds the OBFileSpec object, which specifies the items to include or exclude from a backup, to the backup policy (OBPolicy object).

## SYNTAX

```
Add-OBFileSpec [-Policy] <CBPolicy> [-FileSpec] <CBFileSpec[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-OBFileSpec** cmdlet adds the OBFileSpec object, which specifies the items to include or exclude from a backup, to the backup policy (OBPolicy object).
The OBFileSpec object can include or exclude multiple files, folders, or volumes.
The list of items to include can be defined by using the New-OBFileSpec cmdlet and then update the OBPolicy object using this cmdlet.
The **Add-OBFileSpec** cmdlet supports **WhatIf** and **Confirm** parameters with a low impact.
The low impact signifies that the cmdlet will not prompt the user by default.
The **WhatIf** parameter gives a verbose description of what the cmdlet does.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using **-Confirm:$FALSE** will override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$policy = Get-OBPolicy

PS C:\>New-OBFileSpec -FileSpec "C:\testdata" -NonRecursive | Add-OBFileSpec -Policy $policy
```

This example adds a file specification.

### EXAMPLE 2
```
PS C:\>$fspec = New-OBFileSpec -FileSpec C:\testdata -NonRecursive

PS C:\>New-OBPolicy | Add-OBFileSpec -FileSpec $fspec
```

This example adds a file specification.

## PARAMETERS

### -FileSpec
Specifies the OBFileSpec object to add to the backup policy.

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
Specifies the backup policy (OBPolicy object) to update.

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

[New-OBFileSpec](./New-OBFileSpec.md)

[New-OBPolicy](./New-OBPolicy.md)

