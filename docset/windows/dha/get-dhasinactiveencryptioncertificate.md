---
author: brianlic-msft
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
title: Get-DHASInactiveEncryptionCertificate
ms.assetid: B0BC1A49-BF65-415C-AB83-F085554B5B60
---

# Get-DHASInactiveEncryptionCertificate

## SYNOPSIS
Gets the inactive encryption certificate.

## SYNTAX

```
Get-DHASInactiveEncryptionCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-DHASInactiveEncryptionCertificate** cmdlet gets the inactive encryption certificate thumbprint for the Device Health Attestation service.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Get the inactive encryption certificate
```
PS C:\>Get-DHASInactiveEncryptionCertificate
```

This command gets the inactive encryption certificate thumbprint.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the inactive encryption certificate as a **String**.

## NOTES

## RELATED LINKS

[Remove-DHASInactiveEncryptionCertificate](./Remove-DHASInactiveEncryptionCertificate.md)

