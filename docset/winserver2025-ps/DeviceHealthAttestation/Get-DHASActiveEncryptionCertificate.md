---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
Module Name: DeviceHealthAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/devicehealthattestation/get-dhasactiveencryptioncertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DHASActiveEncryptionCertificate
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
PS C:\> Get-DHASActiveEncryptionCertificate
```

This command gets the thumbprint of the active encryption certificate for the Device Health Attestation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the active encryption certificate thumbprint.

## NOTES

## RELATED LINKS

[Set-DHASActiveEncryptionCertificate](./Set-DHASActiveEncryptionCertificate.md)

