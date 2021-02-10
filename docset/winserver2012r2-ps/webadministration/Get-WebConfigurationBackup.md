---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebConfigurationBackup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7A959FA4-63F7-4DA7-A39B-20076FD83F99
ms.author: v-kaunu
ms.reviewer: brianlic
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

### Example 1: Get a list of the available IIS configuration backups
```
IIS:\>Get-WebConfigurationBackup
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WebConfigurationBackup](./Remove-WebConfigurationBackup.md)

