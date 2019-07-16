---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WBBareMetalRecovery
ms.reviewer:
ms.assetid: D13531F1-43DE-4CDD-95B8-D93961005D4E
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

For more information about bare metal recovery, see [Backup for Bare Metal Recovery](http://technet.microsoft.com/en-us/library/bb795820.aspx) on TechNet.


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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBPolicy
This cmdlet queries a **WBPolicy** object that contains a backup policy to determine whether the server can use backups that use that policy for bare metal recovery.

## OUTPUTS

### Boolean
This cmdlet returns a Boolean value to indicate whether the server can run backups that use a specified policy for bare metal recovery.

## NOTES

## RELATED LINKS

[Backup for Bare Metal Recovery](http://technet.microsoft.com/en-us/library/bb795820.aspx)

[Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md)

[Remove-WBBareMetalRecovery](./Remove-WBBareMetalRecovery.md)

