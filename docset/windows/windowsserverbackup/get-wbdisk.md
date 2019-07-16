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
title: Get-WBDisk
ms.reviewer:
ms.assetid: 89601806-F13E-4C1E-AECC-ECC0CA7758F5
---

# Get-WBDisk

## SYNOPSIS
Gets a list of internal and external disks that are online for the local computer.

## SYNTAX

```
Get-WBDisk [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBDisk** cmdlet gets a list of internal and external disks that are online for the local computer.
You can add these disks to a **WBPolicy** object that contains a backup policy by using the [New-WBBackupTarget](./New-WBBackupTarget.md) cmdlet to specify online disks as backup storage locations.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a list of disks for the local computer
```
PS C:\> $Disks = Get-WBDisk
```

This command gets a list of the disks that are on the system.
You can then use the **WBDisk** object in the variable named $Disks to specify a **WBBackupTarget** object, and use the **WBBackupTarget** object to specify where to store backups for a **WBPolicy** object that contains a backup policy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### WBDisk[]
This cmdlet returns an array of **WBDisk** objects for the hard disks that the cmdlet detects on the local computer.

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Get-WBBackupTarget](./Get-WBBackupTarget.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[Remove-WBBackupTarget](./Remove-WBBackupTarget.md)

