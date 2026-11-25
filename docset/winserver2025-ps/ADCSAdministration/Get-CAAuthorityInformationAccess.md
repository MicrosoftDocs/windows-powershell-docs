---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/get-caauthorityinformationaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CAAuthorityInformationAccess
---

# Get-CAAuthorityInformationAccess

## SYNOPSIS
Gets the AIA and OCSP URI information set on the AIA extension of the CA properties.

## SYNTAX

```
Get-CAAuthorityInformationAccess [<CommonParameters>]
```

## DESCRIPTION
The **Get-CAAuthorityInformationAccess** cmdlet gets the Authority Information Access (AIA) and Online Certificate Status Protocol (OCSP) URI information set on the AIA extension of the certification authority (CA) properties.

## EXAMPLES

### Example 1: Get AIA and OCSP URI information set on the AIA extension of the CA properties
```
PS C:\> Get-CAAuthorityInformationAccess
```

This command gets the current AIA and OCSP settings information for the certification authority.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccess
This cmdlet returns an array of Authority Information Access (AIA) **Microsoft.CertificateServices.Management.Cmdlets.CA.AuthorityInformationAccess** objects.
Each object will contain URI and different Boolean properties as follows:

Name | Type
-----|------
Uri | String
AddToCertificateAia | Boolean
AddtoCertificateOCSP | Boolean

## NOTES

## RELATED LINKS

[Add-CAAuthorityInformationAccess](./Add-CAAuthorityInformationAccess.md)

[Remove-CAAuthorityInformationAccess](./Remove-CAAuthorityInformationAccess.md)

