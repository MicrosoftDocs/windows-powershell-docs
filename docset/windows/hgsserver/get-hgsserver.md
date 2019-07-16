---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsServer-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsServer
ms.assetid: 52EC81F8-5893-499F-BBA2-C7ED12B46D4F
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-HgsServer
ms.reviewer:
---

# Get-HgsServer

## SYNOPSIS
Gets the status of the Host Guardian Service server.

## SYNTAX

```
Get-HgsServer [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsServer** cmdlet gets the status of the Host Guardian Service (HGS) server, including key protection URL(s), attestation URL(s), and the attestation operation mode.

## EXAMPLES

### Example 1: Get the status of the Host Guardian Service server
```
PS C:\> Get-HgsServer
```

This command gets the status of the Host Guardian Service server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[HGS Server Cmdlets](./hgsserver.md)

