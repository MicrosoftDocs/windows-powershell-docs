---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
Module Name: ADCSAdministration
Module Guid: BCC14C75-EDE8-486E-97A5-5BF775C4A221
Download Help Link: http://go.microsoft.com/fwlink/?LinkId=285732
Help Version: 4.0.3.1
Locale: en-US
title: ADCSAdministration
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 12/27/2016
ms.topic: reference
ms.prod: w10
ms.technology: powershell-windows
ms.assetid: 38D3C333-40AB-4E35-943F-6AC57DEB55A7
---

# ADCSAdministration Module
## Description
This topic contains the brief descriptions of the Windows PowerShell® cmdlets that are for use in administering the Active Directory Certificate Services (AD CS) certification authority (CA) role service. Each cmdlet in the table is linked to additional information about that cmdlet.

## ADCSAdministration Cmdlets
### [Add-CAAuthorityInformationAccess](./Add-CAAuthorityInformationAccess.md)
Configures the AIA or OCSP for a certification authority.

### [Add-CACrlDistributionPoint](./Add-CACrlDistributionPoint.md)
Adds a CRL distribution point URI where AD CS publishes certification revocations.

### [Add-CATemplate](./Add-CATemplate.md)
Adds a certificate template to the CA.

### [Backup-CARoleService](./Backup-CARoleService.md)
Backs up the CA database and private key information.

### [Confirm-CAEndorsementKeyInfo](./Confirm-CAEndorsementKeyInfo.md)
Checks whether the local CA trusts secure hardware for key attestation.

### [Get-CAAuthorityInformationAccess](./Get-CAAuthorityInformationAccess.md)
Gets the AIA and OCSP URI information set on the AIA extension of the CA properties.

### [Get-CACrlDistributionPoint](./Get-CACrlDistributionPoint.md)
Gets all the locations set on the CDP extension of the CA properties.

### [Get-CATemplate](./Get-CATemplate.md)
Gets the list of templates set on the CA for issuance of certificates.

### [Remove-CAAuthorityInformationAccess](./Remove-CAAuthorityInformationAccess.md)
Removes AIA or OCSP URI from the AIA extension set on the certification authority.

### [Remove-CACrlDistributionPoint](./Remove-CACrlDistributionPoint.md)
Removes the URI for the CRL distribution point (CDP) from the CA.

### [Remove-CATemplate](./Remove-CATemplate.md)
Removes the templates from the CA which were set for issuance of certificates.

### [Restore-CARoleService](./Restore-CARoleService.md)
Restores the CA database and private key information.


