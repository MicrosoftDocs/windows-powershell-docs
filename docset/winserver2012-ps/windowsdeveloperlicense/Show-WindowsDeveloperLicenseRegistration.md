---
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
ms.assetid: AF54274E-AB48-4A85-8839-CE11B5D6C2E3
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
For more information about developer licenses, see Get a developer license (Windows Store apps) (Windows)http://msdn.microsoft.com/en-us/library/windows/apps/hh974578.aspx (http://msdn.microsoft.com/en-us/library/windows/apps/hh974578.aspx) in the Microsoft Developer Network library.

You need to run the Windows PowerShell® console as Administrator to register a developer license.
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

