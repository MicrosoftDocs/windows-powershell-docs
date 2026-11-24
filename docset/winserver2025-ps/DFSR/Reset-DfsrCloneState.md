---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/reset-dfsrclonestate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-DfsrCloneState
---

# Reset-DfsrCloneState

## SYNOPSIS
Cancels a cloning operation.

## SYNTAX

```
Reset-DfsrCloneState [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-DfsrCloneState** cmdlet cancels an ongoing Distributed File System (DFS) Replication database cloning operation and resets the database of the volume to the previous state.

When you cancel an export, the DFS Replication service restores the backup database copy that it created at the start of the process.
When you cancel an import, the DFS Replication service deletes the new database copy.
When you run the cmdlet, the cmdlet sends the reset and waits for the DFS Replication service to complete.
Use the **Get-DfsrState** cmdlet to determine the current reset status.

## EXAMPLES

### Example 1: Cancel a cloning operation
```
PS C:\> Reset-DfsrCloneState
```

This command cancels the ongoing DFS Replication cloning operation and resets the volume's database to the previous state.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DfsrCloneState](./Get-DfsrCloneState.md)

