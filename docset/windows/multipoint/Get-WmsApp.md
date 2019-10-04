---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WmsApp
ms.reviewer:
ms.assetid: A54B4A6B-98E2-48CE-9814-67BCC78CB796
---

# Get-WmsApp

## SYNOPSIS
Gets a collection of currently running applications in a session.

## SYNTAX

```
Get-WmsApp [-SessionId] <UInt32> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsApp** cmdlet gets a collection of the currently running applications in a specified session.
It also gets the process ID, window ID, and process creation time of the applications.

## EXAMPLES

### Example 1: Get running applications
```
PS C:\> Get-WmsApp -SessionId 3
Name                                                               ProcessId                                WindowId                           CreateTime
----                                                               ------                                   ----                               ----------
Calculator                                                         4228                                     197108                             129937600254314944
```

This command gets the applications that are running in session 3.


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

### -SessionId
Specifies the ID of a Remote Desktop Session (RDS).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
This cmdlet returns a **WmsRunningApp** collection as **PSObject** collection.

## NOTES

## RELATED LINKS

[Close-WmsApp](./Close-WmsApp.md)

[Open-WmsApp](./Open-WmsApp.md)

