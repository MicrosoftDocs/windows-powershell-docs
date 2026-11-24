---
document type: module
HelpInfoUri: https://aka.ms/winsvr-2025-pshelp
Help Version: 1.0.0.0
Locale: en-US
Module Guid: b3e5a5c8-7d2f-4e1a-9c3b-8f6d4a2e1b0c
Module Name: OSLicense
ms.date: 09/11/2026
PlatyPS schema version: 2024-05-01
title: OSLicense Module
---

# OSLicense Module

## Description

The `OSLicense` module provides commands to retrieve Windows licensing information, configure
activation, and manage operating system, Active Directory-based, Key Management Service (KMS),
and subscription licensing.

The module requires Windows PowerShell 5.1. Windows includes it on supported systems. The applicable
Windows update KB number for module availability still needs confirmation.

## OSLicense

### [Get-ADLicenseInfo](Get-ADLicenseInfo.md)

Gets Active Directory-based activation information.

### [Get-KmsLicenseInfo](Get-KmsLicenseInfo.md)

Gets Key Management Service (KMS) licensing information.

### [Get-OSLicenseInfo](Get-OSLicenseInfo.md)

Gets Windows operating system licensing information.

### [Get-SubscriptionLicenseInfo](Get-SubscriptionLicenseInfo.md)

Gets Windows subscription licensing information.

### [Invoke-ADLicense](Invoke-ADLicense.md)

Manages Active Directory-based activation.

### [Invoke-KmsLicense](Invoke-KmsLicense.md)

Clears Key Management Service (KMS) licensing configuration.

### [Invoke-OSLicense](Invoke-OSLicense.md)

Manages Windows operating system product keys, activation, and licenses.

### [Invoke-SubscriptionLicense](Invoke-SubscriptionLicense.md)

Refreshes or removes Windows subscription licenses.

### [Set-KmsLicenseInfo](Set-KmsLicenseInfo.md)

Configures Key Management Service (KMS) licensing settings.

### [Set-OSLicenseInfo](Set-OSLicenseInfo.md)

Sets the Windows operating system license activation type.

### [Set-SubscriptionLicenseInfo](Set-SubscriptionLicenseInfo.md)

Enables or disables Windows subscription licensing.
