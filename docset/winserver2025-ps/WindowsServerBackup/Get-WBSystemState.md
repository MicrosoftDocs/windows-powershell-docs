---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbsystemstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBSystemState
---

# Get-WBSystemState

## SYNOPSIS
Gets a Boolean value that indicates whether system state recovery was added to the backup policy.

## SYNTAX

```
Get-WBSystemState [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBSystemState** cmdlet gets a Boolean value that indicates whether the ability to perform system state recoveries along with the backups was added to the **WBPolicy** object.
If the system state is not in the list of items to be backed up, use the [Add-WBSystemState](./Add-WBSystemState.md) cmdlet to add it to the list.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the system state setting from the backup
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBSystemState -Policy $Policy
```

This example displays a Boolean value that indicates whether the system state setting was added to the **WBPolicy** object that is stored in the variable named $Policy.
The system state setting enables you to use the backups to perform system state recoveries.

The first command stores the result of the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet to the variable named $Policy.

The second command displays the result of the **Get-WBSystemState** cmdlet using the variable named $Policy.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to display.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WBSystemState](./Add-WBSystemState.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBSystemState](./Remove-WBSystemState.md)

