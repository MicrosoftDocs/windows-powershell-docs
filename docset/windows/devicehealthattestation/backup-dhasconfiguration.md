---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Backup-DHASConfiguration
ms.reviewer:
ms.assetid: EE22DE86-88C2-4B94-8A49-27CDC9A91555
---

# Backup-DHASConfiguration

## SYNOPSIS
Backs up the configuration.

## SYNTAX

```
Backup-DHASConfiguration [-Path] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Backup-DHASConfiguration** cmdlet backs up the Device Health Attestation service configuration from the web.config file.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Back up the service configuration
```
PS C:\> Backup-DHASConfiguration -Path "c:\backup.xml"
```

This commands backs up the service configuration from the web.config file to the file specified by the *Path* parameter.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the location in which to save the backup configuration file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns a string with the backup file path.

## NOTES

## RELATED LINKS

[Restore-DHASConfiguration](./Restore-DHASConfiguration.md)

