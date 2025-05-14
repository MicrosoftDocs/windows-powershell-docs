---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfigurationbackup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebConfigurationBackup
---

# Get-WebConfigurationBackup

## SYNOPSIS
Gets a list of available IIS configuration backups.

## SYNTAX

```
Get-WebConfigurationBackup [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigurationBackup** cmdlet gets a list of available Internet Information Services (IIS) configuration backups.

## EXAMPLES

### Example 1: Get available IIS configuration backups
```
IIS:\> Get-WebConfigurationBackup
Name          Creation Date
----          -------------
MyIISBackup   2/25/2009 12:00:00 AM
```

This command returns a list of available IIS configuration backups.

## PARAMETERS

### -Name
Specifies the name of an IIS configuration backup.
If a backup exists that has the specified name, this cmdlet returns information about that backup.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WebConfigurationBackup](./Remove-WebConfigurationBackup.md)

