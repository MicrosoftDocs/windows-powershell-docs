---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: NPS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nps/get-npsradiusclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
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
PS C:\>Get-NpsRadiusClient
```

This command gets a list of all RADIUS clients.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NpsRadiusClient[]

## NOTES

## RELATED LINKS

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Remove-NpsRadiusClient](./Remove-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

