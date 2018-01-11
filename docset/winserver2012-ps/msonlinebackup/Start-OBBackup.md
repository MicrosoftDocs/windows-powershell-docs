---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: E23A375D-129B-43F2-AEFB-BEE4ADA76282
---

# Start-OBBackup

## SYNOPSIS
Starts a one-time backup operation based on the specified OBPolicy.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-OBBackup [-Name] <String> [-Async] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Start-OBBackup [-Policy] <CBPolicy> [-Async] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-OBBackup** cmdlet starts a one-time backup operation.
Set the **Policy** parameter to specify the settings for the backup.

This cmdlet supports WhatIf and Confirm parameters with a medium impact.
The medium impact signifies that the cmdlet will not prompt the user for confirmation by default.
The WhatIf parameter gives a verbose description of what the cmdlet does without performing any operation.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using -Confirm:$FALSE will override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBPolicy | Start-OBBackup
```

This example starts a backup job using a policy.

### EXAMPLE 2
```
PS C:\>Start-OBBackup -Name myPolicy -Async
```

This example starts a backup job by policy name.

## PARAMETERS

### -Async
Allows the user to indicate that the cmdlet should run asynchronously.
This is useful with cmdlets that take a long time to complete.
The control returns to the user immediately after the operation.

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

### -Name
Specifies the policy to be started by name.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies the policy to be backed up.

```yaml
Type: CBPolicy
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### Microsoft.Internal.CloudBackup.Client.Cmdlets.OBJob
This cmdlet displays the status of the currently running backup if the **Async** parameter is not specified.
The Get-OBJob cmdlet can also be used to get the status of the currently running backup operation.

## NOTES

## RELATED LINKS

[Get-OBJob](./Get-OBJob.md)

