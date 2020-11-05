---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Disable-WebCentralCertProvider
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 815BE835-30BE-4ABB-B518-FF2E47F35A94
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-WebCentralCertProvider

## SYNOPSIS
Takes the central certificate provider offline.

## SYNTAX

```
Disable-WebCentralCertProvider [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WebCentralCertProvider** cmdlet takes the central certificate provider offline.
Use the Set-WebCentralCertProvider cmdlet  to re-enable the provider.

## EXAMPLES

### Example 1: Disable the central certificate providerthe central certificate
```
PS C:\>Disable-WebCentralCertProvider
```

This command takes the central certificate provider offline.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Enable-WebCentralCertProvider](./Enable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

