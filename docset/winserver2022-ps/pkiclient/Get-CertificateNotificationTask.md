---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-CertificateNotificationTask
ms.reviewer:
ms.assetid: 7B652875-587E-4E6E-838C-BDA9BFC67FC8
---

# Get-CertificateNotificationTask

## SYNOPSIS
Returns all registered certificate notification tasks.

## SYNTAX

```
Get-CertificateNotificationTask [<CommonParameters>]
```

## DESCRIPTION
The **Get-CertificateNotificationTask** cmdlet returns all certificate notification tasks currently registered by the New-CertificateNotificationTask cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-CertificateNotificationTask
```

This example gets all certificate notification tasks currently registered by the New-CertificateNotificationTask cmdlet.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
None

## OUTPUTS

### Microsoft.CertificateServices.Command.CertificateNotificationTask
This cmdlet returns a **CertificateNotificationTask** object for each certificate notification task that is currently registered by the New-CertificateNotificationTask cmdlet.

## NOTES

## RELATED LINKS

[New-CertificateNotificationTask](./New-CertificateNotificationTask.md)

[Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)

[Switch-Certificate](./Switch-Certificate.md)

