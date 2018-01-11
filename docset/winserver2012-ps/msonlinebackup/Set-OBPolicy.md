---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: A136D91A-7BAA-405F-B5C3-89C65180D56E
---

# Set-OBPolicy

## SYNOPSIS
Sets the OBPolicy object as the backup policy that will be used for scheduled backups.

## SYNTAX

```
Set-OBPolicy [-Policy] <CBPolicy> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-OBPolicy** cmdlet sets the specified OBPolicy object as the backup policy that will be used for scheduled backups.

This cmdlet supports the *WhatIf* and the *Confirm* parameters.
The cmdlet prompts the user for confirmation by default.
The *WhatIf* parameter gives a verbose description of what the cmdlet does without performing any operation.
The *Confirm* parameter specifies whether the cmdlet should prompt the user.
Specify `-Confirm:$FALSE`  to override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$fspec = New-OBFileSpec -FileSpec C:\test\texttext1.txt



PS C:\>$rpolicy = New-OBRetentionPolicy



PS C:\>$sch = New-OBSchedule



PS C:\>New-OBPolicy | Add-OBFileSpec -FileSPec $fspec | Set-OBRetentionPolicy -RetentionPolicy $rpolicy | Set-OBSchedule -Schedule $sch | Set-OBPolicy
```

This example sets a new mob_name_1 policy for a server.

## PARAMETERS

### -Policy
Specifies the current OBPolicy object be set as the active backup policy for the server.

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

### Microsoft.Internal.CloudBackup.Commands.OBPolicy

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicy
This cmdlet sets the OBPolicy object as the backup policy to use for scheduled backups.

## NOTES

## RELATED LINKS

[Add-OBFileSpec](./Add-OBFileSpec.md)

[Get-OBPolicy](./Get-OBPolicy.md)

[New-OBFileSpec](./New-OBFileSpec.md)

[New-OBPolicy](./New-OBPolicy.md)

[New-OBRetentionPolicy](./New-OBRetentionPolicy.md)

[New-OBSchedule](./New-OBSchedule.md)

[Set-OBRetentionPolicy](./Set-OBRetentionPolicy.md)

[Set-OBSchedule](./Set-OBSchedule.md)

