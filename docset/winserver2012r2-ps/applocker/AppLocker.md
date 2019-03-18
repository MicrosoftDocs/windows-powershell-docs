---
Module Name: AppLocker
Module Guid: 9DAFD409-67DE-4108-8EE9-73CD61F5B7BF
Download Help Link: http://go.microsoft.com/fwlink/?LinkId=285540
Help Version: 4.0.2.0
Locale: en-US
title: AppLocker
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: brianlic
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1aeef434-5587-4ec1-9854-222d707bc362
---

# AppLocker Module
## Description
The Windows PowerShell cmdlets for AppLocker are designed to streamline the administration of application control policies. The cmdlets can be used to help author, test, maintain, and troubleshoot application control policies and can be used in conjunction with the AppLocker user interface that is accessed through the Microsoft Management Console (MMC) snap-in extension to the Local Security Policy snap-in and Group Policy Management Console.

## AppLocker Cmdlets
### [Get-AppLockerFileInformation](./Get-AppLockerFileInformation.md)
Gets the file information necessary to create AppLocker rules from a list of files or an event log.

### [Get-AppLockerPolicy](./Get-AppLockerPolicy.md)
Gets the local, the effective, or a domain AppLocker policy.

### [New-AppLockerPolicy](./New-AppLockerPolicy.md)
Creates a new AppLocker policy from a list of file information and other rule creation options.

### [Set-AppLockerPolicy](./Set-AppLockerPolicy.md)
Sets the AppLocker policy for the specified Group Policy Object (GPO).

### [Test-AppLockerPolicy](./Test-AppLockerPolicy.md)
Specifies the AppLocker policy to determine whether the input files will be allowed to run for a given user.

