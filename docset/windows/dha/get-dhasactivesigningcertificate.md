---
author: brianlic
description: 
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DHASActiveSigningCertificate
ms.assetid: 42CF6294-85A1-40C4-9CBA-9F92257D7B24
---

# Get-DHASActiveSigningCertificate

## SYNOPSIS
Gets the active signing certificate.

## SYNTAX

```
Get-DHASActiveSigningCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-DHASActiveSigningCertificate** cmdlet gets the active signing certificate thumbprint for the Device Health Attestation service.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Get the active signing certificate
```
PS C:\>
```

This command gets the active signing certificate thumbprint for the Device Health Attestation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the active signing certificate thumbprint.

## NOTES

## RELATED LINKS

[Set-DHASActiveSigningCertificate](./Set-DHASActiveSigningCertificate.md)

