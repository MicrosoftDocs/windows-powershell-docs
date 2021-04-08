---
author: Kateyanne
external help file: WSBackup_Cmdlets.xml
manager: dansimp
Module Name: WindowsServerBackup
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/stop-wbjob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-WBJob

## SYNOPSIS
Stops the current backup or recovery job.

## SYNTAX

```
Stop-WBJob [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-WBJob** cmdlet stops the backup or recovery job that is currently running.

## EXAMPLES

### Example 1: Stop the current backup job
```
PS C:\> Stop-WBJob
```

This command stops the currently running backup or recovery job.

## PARAMETERS

### -Force
Indicates that the cmdlet stops the backup or recovery job without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
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

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS



[Get-WBJob](./Get-WBJob.md)

