---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NPS.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-NpsRadiusClient
ms.reviewer:
ms.assetid: 575A8489-73DB-4C77-BB77-15971D5D159B
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

