---
document type: module
Help Version: 1.0.0.0
HelpInfoUri:
Locale: en-US
Module Guid: b3e5a5c8-7d2f-4e1a-9c3b-8f6d4a2e1b0c
Module Name: OSLicense
ms.date: 09/07/2026
PlatyPS schema version: 2024-05-01
title: OSLicense Module
---

# OSLicense Module

## Description

The OSLicense module provides commands for managing Windows operating system licensing. You can
use the module to retrieve licensing information, configure activation, and perform operating
system, Active Directory-based, Key Management Service (KMS), and subscription licensing
operations.

The module requires Windows PowerShell 5.1 and is installed with Windows on supported systems. The
applicable Windows update KB number for module availability is pending confirmation.

## OSLicense

### [Get-ADLicenseInfo](Get-ADLicenseInfo.md)

Gets Active Directory-based activation information.

### [Get-OSLicenseInfo](Get-OSLicenseInfo.md)

Gets Windows operating system licensing information.

### [Invoke-ADLicense](Invoke-ADLicense.md)

Performs Active Directory-based activation operations.

### [Invoke-KmsLicense](Invoke-KmsLicense.md)

Clears Key Management Service (KMS) licensing configuration.

### [Invoke-OSLicense](Invoke-OSLicense.md)

Performs Windows operating system product key, activation, and license management operations.

### [Invoke-SubscriptionLicense](Invoke-SubscriptionLicense.md)

Performs Windows subscription license refresh and removal operations.

### [Set-KmsLicenseInfo](Set-KmsLicenseInfo.md)

Configures Key Management Service (KMS) licensing settings.

### [Set-OSLicenseInfo](Set-OSLicenseInfo.md)

Sets the Windows operating system license activation type.

### [Set-SubscriptionLicenseInfo](Set-SubscriptionLicenseInfo.md)

Enables or disables Windows subscription licensing.
