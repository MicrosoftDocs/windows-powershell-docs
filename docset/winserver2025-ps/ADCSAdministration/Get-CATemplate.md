---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/get-catemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CATemplate
---

# Get-CATemplate

## SYNOPSIS
Gets the list of templates set on the CA for issuance of certificates.

## SYNTAX

```
Get-CATemplate [<CommonParameters>]
```

## DESCRIPTION
The **Get-CATemplate** cmdlet gets the list of templates set on the certificate authority (CA) for issuance of certificates.

## EXAMPLES

### Example 1: Get the list of templates set on the CA for issuance of certificates
```
PS C:\> Get-CATemplate
```

This command gets a list of certificate template entries that each contain a template name.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.Common.CertificateTemplate
This cmdlet returns an array of certificate template objects which have two properties: (1) Object Name and (2) Object ID (OID).
Both properties are of string type.

## NOTES

## RELATED LINKS

[Add-CATemplate](./Add-CATemplate.md)

[Remove-CATemplate](./Remove-CATemplate.md)

