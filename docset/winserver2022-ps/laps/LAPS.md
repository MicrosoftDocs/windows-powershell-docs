---
description: This reference provides cmdlet descriptions and syntax for the Windows Local Administrator Password Solution (LAPS) module.
Module Name: LAPS
Module Guid: 8eb7ddf9-7890-49ae-9af1-3b41d7e63c41
Download Help Link: https://aka.ms/winsvr-2022-pshelp
Help Version: 1.0.0.0
Locale: en-US
ms.date: 04/10/2023
title: LAPS
---

# LAPS Module

## Description

This reference provides cmdlet descriptions and syntax for the Windows Local Administrator Password
Solution (LAPS) module. It lists the cmdlets in alphabetical order.

## LAPS Cmdlets

### [Find-LapsADExtendedRights](Find-LapsADExtendedRights.md)

Queries Active Directory (AD) to find principals that have been granted permission to read Windows
Local Administrator Password Solution (LAPS) password attributes.

### [Get-LapsAADPassword](Get-LapsAADPassword.md)

Queries Azure Active Directory (AAD) for the Windows Local Administrator Password Solution (LAPS)
credentials on a specified Azure AD device.

### [Get-LapsADPassword](Get-LapsADPassword.md)

Queries Windows Local Administrator Password Solution (LAPS) credentials from Active Directory (AD)
on a specified AD computer or domain controller object.

### [Get-LapsDiagnostics](Get-LapsDiagnostics.md)

Collects Windows Local Administrator Password Solution (LAPS) logs and tracing from the local
machine.

### [Invoke-LapsPolicyProcessing](Invoke-LapsPolicyProcessing.md)

Causes Windows Local Administrator Password Solution (LAPS) to process the currently configured
policy.

### [Reset-LapsPassword](Reset-LapsPassword.md)

Causes Windows Local Administrator Password Solution (LAPS) to immediately rotate the password for
the currently managed local account.

### [Set-LapsADAuditing](Set-LapsADAuditing.md)

Configures an Active Directory (AD) Organizational Unit (OU) to enable auditing on the Windows Local
Administrator Password Solution (LAPS) password schema attributes.

### [Set-LapsADComputerSelfPermission](Set-LapsADComputerSelfPermission.md)

Configures permissions on an Active Directory (AD) Organizational Unit (OU) to enable computers in
that OU to update their Windows Local Administrator Password Solution (LAPS) passwords.

### [Set-LapsADPasswordExpirationTime](Set-LapsADPasswordExpirationTime.md)

Sets the Windows Local Administrator Password Solution (LAPS) password expiration timestamp on an
Active Directory (AD) computer or domain controller object.

### [Set-LapsADReadPasswordPermission](Set-LapsADReadPasswordPermission.md)

Configures security on an Active Directory (AD) Organizational Unit (OU) to grant specific users or
groups permission to query Windows Local Administrator Password Solution (LAPS) passwords.

### [Set-LapsADResetPasswordPermission](Set-LapsADResetPasswordPermission.md)

Configures security on an Active Directory (AD) Organizational Unit (OU) to grant specific users or
groups permission to set the Windows Local Administrator Password Solution (LAPS) password
expiration time.

### [Update-LapsADSchema](Update-LapsADSchema.md)

Extends the Active Directory (AD) schema with the Windows Local Administrator Password Solution
(LAPS) schema attributes.
