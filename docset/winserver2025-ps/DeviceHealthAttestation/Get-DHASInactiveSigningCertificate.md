---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
Module Name: DeviceHealthAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/devicehealthattestation/get-dhasinactivesigningcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DHASInactiveSigningCertificate
---

# Get-DHASInactiveSigningCertificate

## SYNOPSIS
Gets the inactive signing certificate.

## SYNTAX

```
Get-DHASInactiveSigningCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-DHASInactiveSigningCertificate** cmdlet gets the inactive signing certificate thumbprint for the Device Health Attestation service.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Get the inactive signing certificate
```
PS C:\> Get-DHASInactiveSigningCertificate
```

This example gets the inactive signing certificate thumbprint.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-DHASInactiveSigningCertificate](./Remove-DHASInactiveSigningCertificate.md)

