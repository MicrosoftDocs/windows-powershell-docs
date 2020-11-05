---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssComputer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 81FAD8F5-E1C1-4179-ACB8-0E3A23F1DAEE
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssComputer

## SYNOPSIS
Gets device information objects for the computers in a network.

## SYNTAX

```
Get-WssComputer [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssComputer** cmdlet gets the device information objects for the computers in a network.
A **DeviceInfo** object contains the properties for a computer.
The cmdlet gets **DeviceInfo** objects for servers, clients, and archived clients.
An archived client is a backup of a computer that is no longer part of the network.

## EXAMPLES

### Example 1: Get properties for computers in a network
```
PS C:\> Get-WssComputer
```

This command gets the **DeviceInfo** objects for the computers in the network.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Common.Devices.DeviceInfo
A **DeviceInfo** object contains all the properties for a computer in the network.

## NOTES

## RELATED LINKS

[Remove-WssComputer](./Remove-WssComputer.md)

