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
title: Restore-WBCatalog
ms.reviewer:
ms.assetid: 577E6C4C-DE75-444F-B3A0-0BAD00620895
---

# Restore-WBCatalog

## SYNOPSIS
Restores a backup catalog for the local computer from a storage location.

## SYNTAX

```
Restore-WBCatalog [-BackupTarget] <WBBackupTarget> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-WBCatalog** cmdlet restores a backup catalog for the local computer from a storage location that you specify.

If the location (disk, DVD, or remote shared folder) where you store your backups is damaged or lost and you cannot use it to restore the backup catalog, use this cmdlet to remove the corrupted catalog.
Then create a new backup after the cmdlet finishes removing your backup catalog.

## EXAMPLES

### Example 1: Restore a backup catalog
```
PS C:\> Restore-WBCatalog -BackupTarget $Bt -Force
3 backups found in the specified target. 
WARNING: The backup information on this location has details of backups created
up to 12/8/2011 11:41:38 AM. You may not be able to access backups created
after this date when the catalog recovery operation completes. 
The catalog has been successfully recovered.
```

This command recovers the backup catalog from the backup target stored in the variable named $Bt.
The cmdlet displays a warning that gives details about the backups present in the backup target.
The cmdlet also displays a message that confirms that it has successfully recovered the catalog.

## PARAMETERS

### -BackupTarget
Specifies a backup target object that contains the storage location where backups from which the cmdlet restores the catalog reside.

```yaml
Type: WBBackupTarget
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBBackupTarget, SwitchParameter
Specifies a backup target object from which to restore the catalog.
Use the *Force* parameter to suppress the confirmation message.

## OUTPUTS

### System.String
This cmdlet returns a warning that gives details about the backups present in the backup target and a message that confirms that the cmdlet successfully recovered the catalog.

## NOTES

## RELATED LINKS

[Remove-WBCatalog](./Remove-WBCatalog.md)

