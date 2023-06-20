---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: AppX
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/appx/get-appxpackage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppxPackage
---

# Get-AppxPackage

## SYNOPSIS
Gets a list of the app packages (.appx) that are installed in a user profile.

## SYNTAX

```
Get-AppxPackage [-AllUsers] [-PackageTypeFilter <PackageTypes>] [[-Name] <String>] [[-Publisher] <String>]
 [-User <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxPackage** cmdlet gets a list of the app packages (.appx) that are installed in a user profile.
To get the list of packages for a user profile other than the profile for the current user, you must run this command by using administrator permissions.

## EXAMPLES

### Example 1
```
PS C:\>Get-AppxPackage -AllUsers
```

This command lists the app packages (.appx) that are installed for every user account on the computer.

### Example 2
```
PS C:\>Get-AppxPackage -Name Package1 -User domain\username
```

This command displays information about Package1 if it's installed in the specified user profile.

## PARAMETERS

### -AllUsers
Lists app packages (.appx) for all user accounts on the computer.
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
If you use this parameter, the cmdlets will return only results for this package.
Wildcards are permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

By default, Get-AppxPackage only returns packages of type: Main and Framework.

```yaml
Type: PackageTypes
Parameter Sets: (All)
Aliases: 
Accepted values: None, Main, Framework, Resource, Bundle

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of a particular package.
If you use this parameter, the cmdlets will return only results for this publisher.
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

### -User
Specifies a user name.
If you use this parameter, the cmdlets will return only a list of app packages (.appx) that are installed for the specified user.
To get the list of packages for a user profile other than the profile for the current user, you must run this command by using administrator permissions.
The user name can be in one of these formats:

-- domain\user_name
-- user_name@fqn.domain.tld
-- user_name
-- SID-string

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage
An AppxPackage object that contain information, including the full name of the app package.

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Add-AppxPackage](./Add-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)

[Get-AppxLog](./Get-AppxLog.md)

[Get-AppxLastError](./Get-AppxLastError.md)

