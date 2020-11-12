---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WmsScheduledUpdate
ms.reviewer:
ms.assetid: 2E21030B-CE4F-41D5-AB0A-B16AC7EFAC49
---

# Get-WmsScheduledUpdate

## SYNOPSIS
Gets the scheduled update configuration.

## SYNTAX

```
Get-WmsScheduledUpdate [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsScheduledUpdate** cmdlet gets the current configuration for scheduled updates while disk protection is set to discard mode.

## EXAMPLES

### Example 1: Get the scheduled update configuration
```
PS C:\> Get-WmsScheduledUpdate

IsScheduleUpdateEnabled       : True
AutomaticUpdateMode           : WindowsOnly
HourToScheduleUpdates         : 3
CustomScript                  : c:\myapps\sampleapp.exe
MaxTimeAllowedForCustomScript : 30
ReturnState                   : PreviousState
```

This command gets the current scheduled update configuration.

## PARAMETERS

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WmsScheduledUpdate

## NOTES

## RELATED LINKS

[Disable-WmsScheduledUpdate](./Disable-WmsScheduledUpdate.md)

[Enable-WmsScheduledUpdate](./Enable-WmsScheduledUpdate.md)

[Set-WmsScheduledUpdate](./Set-WmsScheduledUpdate.md)

