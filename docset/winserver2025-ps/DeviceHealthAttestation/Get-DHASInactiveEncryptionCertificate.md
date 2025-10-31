---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
Module Name: DeviceHealthAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/devicehealthattestation/get-dhasinactiveencryptioncertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DHASInactiveEncryptionCertificate
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
PS C:\> Get-DHASInactiveEncryptionCertificate
```

This command gets the inactive encryption certificate thumbprint.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the inactive encryption certificate as a **String**.

## NOTES

## RELATED LINKS

[Remove-DHASInactiveEncryptionCertificate](./Remove-DHASInactiveEncryptionCertificate.md)

