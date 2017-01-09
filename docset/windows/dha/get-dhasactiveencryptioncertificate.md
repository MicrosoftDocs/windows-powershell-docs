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
title: Get-DHASActiveEncryptionCertificate
ms.assetid: 6B9DC3DB-8A35-438F-92CE-67A7444C9C41
---

# Get-DHASActiveEncryptionCertificate

## SYNOPSIS
Gets the active encryption certificate thumbprint.

## SYNTAX

```
Get-DHASActiveEncryptionCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-DHASActiveEncryptionCertificate** cmdlet gets the active encryption certificate thumbprint for the Device Health Attestation service.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Get the active encryption certificate
```
PS C:\>Get-DHASActiveEncryptionCertificate
```

This command gets the thumbprint of the active encryption certificate for the Device Health Attestation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the active encryption certificate thumbprint.

## NOTES

## RELATED LINKS

[Set-DHASActiveEncryptionCertificate](./Set-DHASActiveEncryptionCertificate.md)

