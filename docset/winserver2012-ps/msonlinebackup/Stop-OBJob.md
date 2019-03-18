---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 81E2B06C-0E1E-4637-A893-4D3913FB850B
---

# Stop-OBJob

## SYNOPSIS
Stops the specified backup or recovery job.

## SYNTAX

```
Stop-OBJob [-Job] <CBJob> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-OBJob** cmdlet stops currently running job, such as backup or recovery.

This cmdlet supports the *WhatIf* and the *Confirm* parameters.
The cmdlet prompts the user for confirmation by default.
The *WhatIf* parameter gives a verbose description of what the cmdlet does without performing any operation.
The *Confirm* parameter specifies whether the cmdlet should prompt the user.
Specify `-Confirm:$FALSE` to override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$job = Get-OBJob



PS C:\>Stop-OBJob -Job $job
```

This example stops a job.

## PARAMETERS

### -Job
Specifies the job to be stopped.

```yaml
Type: CBJob
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

### Microsoft.Internal.CloudBackup.Client.Cmdlets.OBJob

## NOTES

## RELATED LINKS

[Get-OBJob](./Get-OBJob.md)

