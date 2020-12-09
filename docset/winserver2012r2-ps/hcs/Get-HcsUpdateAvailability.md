---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-HcsUpdateAvailability
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8264BDCA-CDC8-415C-B322-B24D41BAA282
---

# Get-HcsUpdateAvailability

## SYNOPSIS
Scans for updates.

## SYNTAX

```
Get-HcsUpdateAvailability [-UpdateId <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsUpdateAvailability** cmdlet scans for updates.
The cmdlet tells you which updates are maintenance mode updates and which are normal updates.
A maintenance mode update requires maintenance mode.

## EXAMPLES

### Example 1: Check for updates
```
PS C:\>Get-HcsUpdateAvailability
```

This command checks for available updates for your device.

## PARAMETERS

### -UpdateId
Specifies an update ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Patching.HCSUpdateSearchResults
The HCSUpdateSearchResults object has the following properties:

- RegularUpdates 
- MaintenanceModeUpdates

## NOTES

## RELATED LINKS

[Get-HcsUpdateStatus](./Get-HcsUpdateStatus.md)

[Start-HcsUpdate](./Start-HcsUpdate.md)

[Start-HcsHotfix](./Start-HcsHotfix.md)

