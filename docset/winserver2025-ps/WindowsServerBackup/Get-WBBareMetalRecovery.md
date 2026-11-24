---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbbaremetalrecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBBareMetalRecovery
---

# Get-WBBareMetalRecovery

## SYNOPSIS
Gets a Boolean value that indicates whether or not a backup policy can perform bare metal recoveries from backups.

## SYNTAX

```
Get-WBBareMetalRecovery [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBBareMetalRecovery** cmdlet gets a Boolean value that indicates whether or not a **WBPolicy** object that contains a backup policy can perform bare metal recoveries from backups.
A bare metal recovery is the process of rebuilding a computer after a catastrophic failure.
The recovery process backs up the system volume and master boot record by copying the entire volume and using Volume Shadow Copy Service (VSS) writers to ensure that all applications are in a consistent state for the copy.

For more information about bare metal recovery, see [Backup for Bare Metal Recovery](https://technet.microsoft.com/en-us/library/bb795820.aspx) on TechNet.


If a policy does not include the ability to perform bare metal recoveries from backups, use the [Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md) cmdlet to add this ability.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Determine whether a backup policy includes bare metal recovery
```
PS C:\> Get-WBBareMetalRecovery -Policy $Policy
```

This command gets a Boolean value that indicates whether bare metal recovery is set in the **WBPolicy** object and stores this value in the variable named $Policy.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy for which to display information.

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

[Backup for Bare Metal Recovery](https://technet.microsoft.com/en-us/library/bb795820.aspx)

[Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md)

[Remove-WBBareMetalRecovery](./Remove-WBBareMetalRecovery.md)

