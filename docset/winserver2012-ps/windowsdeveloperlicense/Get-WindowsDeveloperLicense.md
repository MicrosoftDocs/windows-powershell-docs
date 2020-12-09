---
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
ms.assetid: 73687EB6-DAF8-4003-BDB3-5599E543F67E
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WindowsDeveloperLicense

## SYNOPSIS
Provides information about a developer license for the current computer.

## SYNTAX

```
Get-WindowsDeveloperLicense [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsDeveloperLicense** cmdlet provides information about the developer license present on the current computer.
For more information about developer licenses, see Get a developer license (Windows Store apps) (Windows)http://msdn.microsoft.com/en-us/library/windows/apps/hh974578.aspx (http://msdn.microsoft.com/en-us/library/windows/apps/hh974578.aspx) in the Microsoft Developer Network library.

The cmdlet gets an object that contains the expiration date for the developer license and a Boolean value that indicates whether that license is valid.
If the cmdlet does not find a developer license, it informs you that there is no developer license on the current computer.

## EXAMPLES

### Example 1: Get developer license status
```
PS C:\> Get-WindowsDeveloperLicense
```

This command checks for a developer license for the current computer.
If there is a license on the computer, the cmdlet displays whether it is valid and when it expires.
If the computer does not have a developer license, the cmdlet returns an error.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WindowsDeveloperLicense

## NOTES

## RELATED LINKS

[Unregister-WindowsDeveloperLicense](./Unregister-WindowsDeveloperLicense.md)

[Show-WindowsDeveloperLicenseRegistration](./Show-WindowsDeveloperLicenseRegistration.md)

