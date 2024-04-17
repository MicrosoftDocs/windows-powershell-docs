---
description: The LanguagePackManagement module includes cmdlets that help you easily manage languages and language settings on a running Windows installation
Download Help Link: https://aka.ms/winsvr-2022-pshelp
Help Version: 5.0.0.1
Locale: en-US
Module Guid: f42dbdd4-4358-4067-8155-a4567a0aaee5
Module Name: LanguagePackManagement
ms.date: 08/15/2022
title: LanguagePackManagement module
---

# LanguagePackManagement Module
## Description

This module can be used to easily [add languages](/windows-hardware/manufacture/desktop/available-language-packs-for-windows) and [related language features](/windows-hardware/manufacture/desktop/features-on-demand-language-fod) and manage settings like System Preferred UI Language, System Locale, Input method (Keyboard), Locale, Speech Recognizer, User Preferred Language List using the new cmdlets.   

> [!NOTE]
> - These cmdlets are supported on client operating system only. 
> - To run the `Install-Language` and `Set-Language` cmdlets you must run the PowerShell as an admin (right click on the icon). 
> - These cmdlets work in conjunction with the [International module](/powershell/module/international/), which allows users to control the language used for various elements of the user interface (UI).
> - The `Install-Language` cmdlet can only install Windows display language resources for [Language Pack languages](/windows-hardware/manufacture/desktop/available-language-packs-for-windows).

## LanguagePackManagement Cmdlets
### [Get-InstalledLanguage](Get-InstalledLanguage.md)
Returns information about the installed languages on a device.

### [Get-SystemPreferredUILanguage](Get-SystemPreferredUILanguage.md)
Returns the current System Preferred Language.

### [Install-Language](Install-Language.md)
Installs a language onto a device.

### [Set-SystemPreferredUILanguage](Set-SystemPreferredUILanguage.md)
Sets the provided language as the System Preferred UI Language.

### [Uninstall-Language](Uninstall-Language.md)
Removes a language from a device.
