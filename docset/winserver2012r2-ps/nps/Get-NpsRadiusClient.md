---
author: Kateyanne
description: 
external help file: Microsoft.NPS.Commands.dll-Help.xml
manager: jasgro
Module Name: NPS
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/nps/get-npsradiusclient?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NpsRadiusClient
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

