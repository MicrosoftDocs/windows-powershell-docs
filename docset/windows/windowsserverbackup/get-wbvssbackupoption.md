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
title: Get-WBVssBackupOption
ms.reviewer:
ms.assetid: 0B8B0A93-ED16-4E01-9140-5F8386D8803D
---

# Get-WBVssBackupOption

## SYNOPSIS
Gets a VSS setting from the backup policy.

## SYNTAX

```
Get-WBVssBackupOption [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBVSSBackupOption** cmdlet gets a setting that determines whether the backups created through the **WBPolicy** object are Volume Shadow Copy Service (VSS) copy backups or VSS full backups.
For more information about VSS copy backups and VSS full backups, or to change this setting, refer to the [Set-WBVssBackupOption](./Set-WBVssBackupOption.md) cmdlet.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the VSS setting from the backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBVssBackupOption -Policy $Policy
```

This example gets the VSS setting, either VssCopyBackup or VssFullBackup.

The first command stores the result of the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet in the variable named $Policy.

The second command gets the VSS setting from the variable $Policy.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object that this cmdlet gets.

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
This cmdlet queries the **WBPolicy** object.

## OUTPUTS

### Microsoft.Windows.ServerBackup.Commands.VssBackupOptions
This cmdlet returns either a **VssCopyBackup** or **VssFullBackup** object, depending on the option specified in the **WBPolicy** object.

## NOTES

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Set-WBVssBackupOption](./Set-WBVssBackupOption.md)

