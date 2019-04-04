---
Module Name: SecureBoot
Module Guid: A5BD98E1-E44C-44FB-B88F-5AF9BDE66FDF
Download Help Link: http://go.microsoft.com/fwlink/?linkid=285772
Help Version: 4.0.1.0
Locale: en-US
title: SecureBoot
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 52fb92c0-691b-4f78-afa1-dba0a7988728
ms.author: kenwith
ms.reviewer: brianlic
---

# SecureBoot Module
## Description
This reference provides cmdlet descriptions and syntax for all Secure Boot-specific cmdlets. It lists the cmdlets in alphabetical order.

## SecureBoot Cmdlets
### [Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)
Confirms that Secure Boot is enabled by checking the Secure Boot status on the local computer.

### [Format-SecureBootUEFI](./Format-SecureBootUEFI.md)
Formats certificates or hashes into a content object that is returned and creates a file that is ready to be signed.

### [Get-SecureBootPolicy](./Get-SecureBootPolicy.md)
Gets the publisher GUID and the policy version of the Secure Boot configuration policy.

### [Get-SecureBootUEFI](./Get-SecureBootUEFI.md)
Gets the UEFI variable values related to Secure Boot such as the SetupMode, SecureBoot, KEK, PK, SignatureDatabase, and forbidden SignatureDatabase.

### [Set-SecureBootUEFI](./Set-SecureBootUEFI.md)
Sets the Secure Boot-related UEFI variables such as Platform Key, Key Exchange Key, Signature Database and Forbidden Signature Database.
