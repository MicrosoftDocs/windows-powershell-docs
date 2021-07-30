---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/appx/get-appxpackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppxPackage
---

# Get-AppxPackage

## SYNOPSIS
Gets a list of the app packages that are installed in a user profile.

## SYNTAX

```
Get-AppxPackage [-AllUsers] [-PackageTypeFilter <PackageTypes>] [[-Name] <String>] [[-Publisher] <String>]
 [-User <String>] [-Volume <AppxVolume>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxPackage** cmdlet gets a list of the app packages that are installed in a user profile.
An app package has an .msix or .appx file name extension.
To get the list of packages for a user profile other than the profile for the current user, you must run this command by using administrator permissions.

## EXAMPLES

### Example 1: Get all app packages for every user account
```
PS C:\> Get-AppxPackage -AllUsers
```

This command lists the app packages that are installed for every user account on the computer.

### Example 2: Get an app package for a specific a user
```
PS C:\> Get-AppxPackage -Name "Package17" -User "Contoso\EvanNarvaez"
```

This command displays information about Package17 if it is installed in the specified user profile.

## PARAMETERS

### -AllUsers
Indicates that this cmdlet lists app packages for all user accounts on the computer.
To use this parameter, you must run the command by using administrator permissions.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a particular package.
If you specify this parameter, the cmdlet returns results for this package only.
Wildcards are permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PackageTypeFilter
Specifies one or more comma-separated types of packages that the cmdlet gets from the package repository.
Valid values are: 

- Bundle
- Framework
- Main
- Resource
- None

By default, this cmdlet returns only packages of types Main and Framework.

```yaml
Type: PackageTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, Main, Framework, Resource, Bundle, Xap

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of a particular package.
If you specify this parameter, the cmdlet returns results only for this publisher.
Wildcards are permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -User
Specifies a user.
If you specify this parameter, the cmdlet returns a list of app packages that are installed for only the user that this cmdlet specifies.
To get the list of packages for a user profile other than the profile for the current user, you must run this command by using administrator permissions.
The user name can be in one of these formats: 

- domain\user_name
- user_name@fqn.domain.tld
- user_name
- SID-string

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Volume
Specifies an **AppxVolume** object.
If you specify this parameter, this cmdlet returns only packages that are relative to volume that this parameter specifies.

```yaml
Type: AppxVolume
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage
This cmdlet returns an **AppxPackage** object that contains information, including the full name of the app package.

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Add-AppxPackage](./Add-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Move-AppxPackage](./Move-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)

