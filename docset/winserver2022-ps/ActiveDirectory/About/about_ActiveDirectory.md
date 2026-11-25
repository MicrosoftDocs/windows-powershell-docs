---
title: about_ActiveDirectory
ms.date: 04/22/2013
description: The Active Directory module is a command line interface for managing Active Directory.
Locale: en-US
schema: 2.0.0
---

# about_ActiveDirectory

## SHORT DESCRIPTION

The Active Directory module is a command line interface for managing Active
Directory.

## LONG DESCRIPTION

The Active Directory module for Windows PowerShell is for IT Professionals who
are administering and interfacing with Active Directory. The Active Directory
module provides an efficient way to complete many administrative,
configuration, and diagnostic tasks across Active Directory Domain Services (AD
DS) and Active Directory Lightweight Directory Services (AD LDS) instances in
their environments. The Active Directory module includes a set of Windows
PowerShell cmdlets and a provider. The provider exposes the Active Directory
database through a hierarchical navigation system, which is very similar to the
file system. As with drives in a file system, such as C:, you can connect
Windows PowerShell drives to Active Directory domains and AD LDS, as well as
Active Directory snapshots.

### Coverage of Active Directory Module Cmdlets

Create, Read, Update, and Delete actions are supported for Active Directory
objects by cmdlets such as `New-ADUser`, `Get-ADOrganizationalUnit`,
`Set-ADComputer`, and `Remove-ADUser`.

Account and Password Policy Management are supported by cmdlets such as
`Enable-ADAccount`, `Unlock-ADAccount`, `New-ADServiceAccount`,
`Set-ADAccountControl`, and `Remove-ADFineGrainedPasswordPolicy`.

Domain and Forest Management is supported by cmdlets such as `Get-ADForest`,
`Set-ADForest`, `Set-ADForestMode`, `Enable-ADOptionalFeature`,
`Get-ADDomainController`, and `Get-ADDomain`.

### Listing the Active Directory Module Cmdlets

To get a list of all of the Active Directory module cmdlets, run

```powershell
Get-Command -Module ActiveDirectory
```

### Getting Started

Getting started with the Active Directory module for Windows PowerShell is as
easy as clicking the following shortcut:

Run the following command in any Windows PowerShell prompt to import the Active
Directory module:

```powershell
Import-Module ActiveDirectory
```

### Overview and Conceptual Topics

The first two of these topics offer a high level overview of the Active
Directory module and the Active Directory Provider.

- For a brief introduction to the Active Directory provider for Windows
  PowerShell, see [ActiveDirectory](/powershell/module/activedirectory).
- The following topics are conceptual support topics for the Active Directory
  module cmdlets.
  - For an introduction to the **Identity** parameter, which is used by the
    Active Directory module cmdlets to identify objects in the directory, see
    [about_ActiveDirectory_Identity](about_ActiveDirectory_Identity.md).
  - For an introduction to the **Filter** parameter which is used by Active
    Directory module cmdlets to search for objects in the directory, see
    [about_ActiveDirectory_Filter](about_ActiveDirectory_Filter.md).
  - For an introduction to the .NET Framework-based object model implemented by
    the Active Directory module, see
    [about_ActiveDirectory_ObjectModel](about_ActiveDirectory_ObjectModel.md).
