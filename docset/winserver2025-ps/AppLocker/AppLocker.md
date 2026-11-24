---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.0.1
Locale: en-US
Module Guid: 9dafd409-67de-4108-8ee9-73cd61f5b7bf
Module Name: AppLocker
ms.date: 09/28/2020
title: AppLocker
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

