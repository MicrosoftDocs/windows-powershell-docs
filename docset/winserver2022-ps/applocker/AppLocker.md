---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
Module Name: AppLocker
Module Guid: 9DAFD409-67DE-4108-8EE9-73CD61F5B7BF
Download Help Link: http://go.microsoft.com/fwlink/?linkid=390751
Help Version: 5.0.0.1
Locale: en-US
title: AppLocker
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 09/28/2020
ms.topic: reference
ms.prod: w10
ms.technology: powershell-windows
ms.assetid: 4BB540B4-DE3E-4ADF-B306-5E714C527017
---

# AppLocker Module
## Description
The Windows PowerShell cmdlets for AppLocker are designed to streamline the administration of application control policies. The cmdlets can be used to help author, test, maintain, and troubleshoot application control policies and can be used in conjunction with the AppLocker user interface that is accessed through the Microsoft Management Console (MMC) snap-in extension to the Local Security Policy snap-in and Group Policy Management Console.

Note that AppLocker cmdlets only interact with group policy and do not have any knowledge of the AppLocker CSP.

## AppLocker Cmdlets
### [Get-AppLockerFileInformation](./Get-AppLockerFileInformation.md)
Gets the file information necessary to create AppLocker rules from a list of files or an event log.

### [Get-AppLockerPolicy](./Get-AppLockerPolicy.md)
Gets the local, the effective, or a domain AppLocker policy.

### [New-AppLockerPolicy](./New-AppLockerPolicy.md)
Creates a new AppLocker policy from a list of file information and other rule creation options.

### [Set-AppLockerPolicy](./Set-AppLockerPolicy.md)
Sets the AppLocker policy for the specified GPO.

### [Test-AppLockerPolicy](./Test-AppLockerPolicy.md)
Specifies the AppLocker policy to determine whether the input files will be allowed to run for a given user.

