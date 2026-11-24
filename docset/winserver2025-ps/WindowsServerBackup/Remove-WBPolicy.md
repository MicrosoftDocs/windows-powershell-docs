---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBPolicy
---

# Remove-WBPolicy

## SYNOPSIS
Removes the backup policy.

## SYNTAX

```
Remove-WBPolicy [[-Policy] <WBPolicy>] [-All] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBPolicy** cmdlet removes the **WBPolicy** object.
This cmdlet stops scheduled daily backups from running.
If the backup storage location is a disk, the cmdlet frees the disk.
If the system does not have a scheduled backup, the cmdlet does not do anything.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove all scheduled backups
```
PS C:\> Remove-WBPolicy -All -Force
```

This command removes the currently set **WBPolicy** object and disables all scheduled backups on the system.
The command also uses the *Force* parameter to suppress the confirmation message.

### Example 2: Remove a specified backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Remove-WBPolicy -Policy $Policy
```

This command store the result of the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet in the variable named $Policy, then removes the **WBPolicy** object, which disables all scheduled backups on the system.

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

### -Policy
Specifies the backup policy object that this cmdlet updates.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### System.Object

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that is set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the *Editable* parameter. The New-WBPolicy cmdlet creates a **WBPolicy** object that is already in edit mode.



## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Set-WBPolicy](./Set-WBPolicy.md)

