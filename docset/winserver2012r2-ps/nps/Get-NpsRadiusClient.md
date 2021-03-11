---
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: Nps
online version: 
schema: 2.0.0
title: Get-NpsRadiusClient
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 1DA52B73-64A9-42E7-9316-371E09E2348A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NpsRadiusClient

## SYNOPSIS
Gets RADIUS clients.

## SYNTAX

```
Get-NpsRadiusClient [<CommonParameters>]
```

## DESCRIPTION
The **Get-NpsRadiusClient** cmdlet gets Remote Authentication Dial-In User Service (RADIUS) clients.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

## EXAMPLES

### Example 1: Get all RADIUS clients
```
PS C:\>$MyRadiusClients = Get-NpsRadiusClient
```

This command gets a list of all RADIUS clients and puts the list in the variable named **$MyRadiusClients**.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NpsRadiusClient[]

## NOTES

## RELATED LINKS

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Remove-NpsRadiusClient](./Remove-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

