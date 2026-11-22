---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/add-wbbaremetalrecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WBBareMetalRecovery
---

# Add-WBBareMetalRecovery

## SYNOPSIS
Adds items to a backup policy so that backups that use the policy can perform bare metal recoveries.

## SYNTAX

```
Add-WBBareMetalRecovery [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WBBareMetalRecovery** cmdlet adds items to a backup policy object so that backups that use that policy can perform bare metal recoveries.
A bare metal recovery is the process of rebuilding a computer after a catastrophic failure.
The recovery process backs up the system volume and master boot record by copying the entire volume and using Volume Shadow Copy Service (VSS) writers to ensure that all applications are in a consistent state for the copy.

For more information about bare metal recovery, see [Backup for Bare Metal Recovery](https://technet.microsoft.com/en-us/library/bb795820.aspx) on TechNet.


If you add the ability to perform a bare metal recovery to a policy, you also add the ability to perform a system state recovery.
This is true even though the **SystemState** property of the bare metal recovery policy has a value of False.

Before you can add a backup target to a **WBPolicy** object, you must put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you have set as the scheduled backup policy, use the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet with the *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add bare metal recovery to a backup policy
```
PS C:\> Add-WBBareMetalRecovery -Policy $Policy
```

This command adds a setting to the **WBPolicy** object in the variable named $Policy to enable the backups that are created through this policy to perform bare metal recovery.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to update.

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

[Get-WBBareMetalRecovery](./Get-WBBareMetalRecovery.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

[Remove-WBBareMetalRecovery](./Remove-WBBareMetalRecovery.md)

