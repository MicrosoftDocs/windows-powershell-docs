---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
Module Name: DeviceHealthAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/devicehealthattestation/get-dhasactivesigningcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DHASActiveSigningCertificate
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
PS C:\> Get-DHASActiveSigningCertificate
```

This command gets the active signing certificate thumbprint for the Device Health Attestation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the active signing certificate thumbprint.

## NOTES

## RELATED LINKS

[Set-DHASActiveSigningCertificate](./Set-DHASActiveSigningCertificate.md)

