---
description: Removes an app package from one or more user accounts.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/remove-appxpackage?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AppxPackage
---

# Remove-AppxPackage

## SYNOPSIS
Removes an app package from one or more user accounts.

## SYNTAX

### RemoveByPackageSet (Default)

```
Remove-AppxPackage [-Package] <String> [-PreserveApplicationData] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RemoveByPackageForRoamingSet

```
Remove-AppxPackage [-Package] <String> [-PreserveRoamableApplicationData] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AllUsersSet

```
Remove-AppxPackage [-Package] <String> [-AllUsers] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserSet

```
Remove-AppxPackage [-Package] <String> -User <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-AppxPackage` cmdlet removes an app package from a user account. An app package has an
`.msix` or `.appx` file extension.

## EXAMPLES

### Example 1: Remove an app package

```powershell
Remove-AppxPackage -Package 'package1_1.0.0.0_neutral__8wekyb3d8bbwe'
```

This command removes an app package named `package1_1.0.0.0_neutral__8wekyb3d8bbwe` from the
account of the current user.

## PARAMETERS

### -AllUsers

This parameter removes the app package for all user accounts on the computer. The parameter works
off the parent package type. If it's a bundle, use **PackageTypeFilter** with the `Get-AppxPackage`
command and specify the bundle. To use this parameter, you must run the command with administrator
permissions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Package

Specifies an **AppxPackage** object or the full name of a package.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreserveApplicationData

Specifies that the cmdlet preserves the application data during the package removal. The
application data is available for later use. Note that this is only applicable for apps that are
under development so this option can only be specified for apps that are registered from file
layout (Loose file registered).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RemoveByPackageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreserveRoamableApplicationData

Preserves the roamable portion of the app's data when the package is removed. This parameter is
incompatible with **PreserveApplicationData**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RemoveByPackageForRoamingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User

If you specify this parameter, the cmdlet removes the app package for only the user that this cmdlet
specifies. To remove a package for a user profile other than the profile of the current user, you
must run this command with administrator permissions.

> [!NOTE]
>
> This parameter only accepts user SIDs. Use the **whoami /user** command to display the current
> SID of a user. See [whoami syntax](/windows-server/administration/windows-commands/whoami) for
> details.

```yaml
Type: System.String
Parameter Sets: UserSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage

An **AppxPackage** object that contain information, including the full name of the app package.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[PackageManager class](https://go.microsoft.com/fwlink/?LinkId=245447)

[Sideload Apps with DISM](https://go.microsoft.com/fwlink/?LinkID=231020)
