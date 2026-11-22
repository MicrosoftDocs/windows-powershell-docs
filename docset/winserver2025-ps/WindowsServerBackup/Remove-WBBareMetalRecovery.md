---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbbaremetalrecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBBareMetalRecovery
---

# Remove-WBBareMetalRecovery

## SYNOPSIS
Removes a request to include items that implement bare metal recovery from the current backup policy.

## SYNTAX

```
Remove-WBBareMetalRecovery [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBBareMetalRecovery** cmdlet removes a request to include items that implement a bare metal recovery from the **WBPolicy** object that contains the current backup policy.
Depending on the contents of the **WBFileSpec** object, the backup process can still back up some items that perform a bare metal recovery, but the backup process itself may not be able to perform a bare metal recovery.

Before you can add a backup target to a **WBPolicy** object, you must put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you have set as the scheduled backup policy, use the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet with the  *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove the ability to perform bare metal recovery from a backup policy
```
PS C:\> Remove-WBBareMetalRecovery -Policy $Policy
```

This command removes the setting to include bare metal recovery from the **WBPolicy** object that is stored in the variable named $Policy.

You cannot use the backups from this policy for bare metal recovery unless the user added all volumes that contain critical system data to the backup policy.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object that contains the backup policy that this cmdlet updates.

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

[Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md)

[Get-WBBareMetalRecovery](./Get-WBBareMetalRecovery.md)

