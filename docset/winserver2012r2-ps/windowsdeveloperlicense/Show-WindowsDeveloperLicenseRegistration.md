---
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
Module Name: WindowsDeveloperLicense
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/windowsdeveloperlicense/show-windowsdeveloperlicenseregistration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Show-WindowsDeveloperLicenseRegistration
---

# Show-WindowsDeveloperLicenseRegistration

## SYNOPSIS
Starts the developer license registration workflow that allows a user to register a developer license.

## SYNTAX

```
Show-WindowsDeveloperLicenseRegistration [<CommonParameters>]
```

## DESCRIPTION
The **Show-WindowsDeveloperLicenseRegistration** cmdlet starts the developer license registration workflow that allows you to create and register a developer license for the current computer.
For more information about developer licenses, see Get a developer license (Windows Store apps) (Windows)http://msdn.microsoft.com/library/windows/apps/hh974578.aspx (http://msdn.microsoft.com/library/windows/apps/hh974578.aspx) in the MSDN library.

You need to run the Windows PowerShell console as Administrator to register a developer license.
You need a valid LiveID.
The Developer License dialog box provides additional information about obtaining a developer license.
If the cmdlet cannot obtain a developer license for you, it returns an error stating that the cmdlet did not register a license.

## EXAMPLES

### Example 1: Register a developer license
```
PS C:\> Show-WindowsDeveloperLicenseRegistration
```

This command opens a dialog box that allows you to register a developer license.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WindowsDeveloperLicense](./Get-WindowsDeveloperLicense.md)

[Unregister-WindowsDeveloperLicense](./Unregister-WindowsDeveloperLicense.md)

