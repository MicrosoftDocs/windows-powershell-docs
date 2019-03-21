---
Module Name: AppLocker
Module Guid: 9DAFD409-67DE-4108-8EE9-73CD61F5B7BF
Download Help Link: http://go.microsoft.com/fwlink/?LinkId=216155
Help Version: 3.1.0.0
Locale: en-US
ms.assetid: 4BB540B4-DE3E-4ADF-B306-5E714C527017
ms.manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
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

