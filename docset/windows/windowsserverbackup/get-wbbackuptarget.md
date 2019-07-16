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
title: Get-WBBackupTarget
ms.reviewer:
ms.assetid: 899D9201-3001-4885-AAA3-EFCC2AF766C2
---

# Get-WBBackupTarget

## SYNOPSIS
Gets backup storage locations that you specified as part of a backup policy.

## SYNTAX

```
Get-WBBackupTarget [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBBackupTarget** cmdlet gets backup storage locations that you specified for a **WBPolicy** object that contains a backup policy.
Valid locations include disks, volumes, or remote shared folders.
To view the list of all online disks, use the [Get-WBDisk](./Get-WBDisk.md) cmdlet.

You can add the locations that the cmdlet returns to a **WBPolicy** object by specifying them as backup storage locations to the [New-WBBackupTarget](./New-WBBackupTarget.md) cmdlet.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a list of backup targets
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBBackupTarget -Policy $Policy
```

This example gets a list of the storage backup locations from a backup policy.

The first command gets the current backup policy and stores it in a variable named $Policy.

The second command gets the list of storage backup locations from the **WBPolicy** object that is stored in the $Policy variable.

## PARAMETERS

### -Policy
Specifies a backup policy object for which this cmdlet displays information.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: InPolicy

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBPolicy
This cmdlet queries the backup policy contained in the specified **WBPolicy** object.

## OUTPUTS

### WBBackupTarget []
This cmdlet returns a list of the storage locations that the backup policy object contains.

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Get-WBDisk](./Get-WBDisk.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[Remove-WBBackupTarget](./Remove-WBBackupTarget.md)

