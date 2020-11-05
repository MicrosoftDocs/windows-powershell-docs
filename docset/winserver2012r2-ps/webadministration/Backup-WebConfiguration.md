---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Backup-WebConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 67560205-D4D2-4BCB-81F1-511B0433963A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Backup-WebConfiguration

## SYNOPSIS
Creates a backup of an IIS configuration.

## SYNTAX

```
Backup-WebConfiguration [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Backup-WebConfiguration** cmdlet creates a backup of an Internet Information Services (IIS) configuration.
The cmdlet creates a folder with the name specified by the **Name** parameter for the backup in the $env:Windir\System32\inetsrv\backup folder.

## EXAMPLES

### Example 1: Backing up an IIS configuration
```
IIS:\>Backup-WebConfiguration -Name "MyIISBackup"

Name           Creation Date

----           -------------

MyIISBackup    2/20/2009 12:00:00 AM
```

This command creates a backup of your IIS configuration in a folder named MyIISBackup.

## PARAMETERS

### -Name
Specifies the name of the folder that this cmdlet creates to store the backup files.
If a backup with the name specified already exists, this cmdlet returns an error.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Add-WebConfiguration](./Add-WebConfiguration.md)

[Clear-WebConfiguration](./Clear-WebConfiguration.md)

[Restore-WebConfiguration](./Restore-WebConfiguration.md)

[Select-WebConfiguration](./Select-WebConfiguration.md)

[Set-WebConfiguration](./Set-WebConfiguration.md)

[Get-WebConfigurationBackup](./Get-WebConfigurationBackup.md)

[Remove-WebConfigurationBackup](./Remove-WebConfigurationBackup.md)

