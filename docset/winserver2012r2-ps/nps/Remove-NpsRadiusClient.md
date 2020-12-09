---
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: Nps
online version: 
schema: 2.0.0
title: Remove-NpsRadiusClient
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 575A8489-73DB-4C77-BB77-15971D5D159B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-NpsRadiusClient

## SYNOPSIS
Removes a RADIUS client.

## SYNTAX

```
Remove-NpsRadiusClient [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NpsRadiusClient** cmdlet removes a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

## EXAMPLES

### Example 1: Remove a RADIUS client
```
PS C:\>Remove-NpsRadiusClient -Name "RadiusClient01"
```

This command removes a RADIUS client named RadiusClient01.

## PARAMETERS

### -Name
Specifies the name of the RADIUS client to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

