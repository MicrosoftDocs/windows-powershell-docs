---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/clear-uevappxpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-UevAppxPackage
---

# Clear-UevAppxPackage

## SYNOPSIS
Clears a setting in the computer or user sections of the registry.

## SYNTAX

### ParameterSetUser (Default)
```
Clear-UevAppxPackage [-CurrentComputerUser] [-PackageFamilyName] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParameterSetComputer
```
Clear-UevAppxPackage [-Computer] [-PackageFamilyName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetAllComputerTemplates
```
Clear-UevAppxPackage [-Computer] [-All] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetAllUserTemplates
```
Clear-UevAppxPackage [-CurrentComputerUser] [-All] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-UevAppxPackage** cmdlet clears a setting in the computer or user sections of the registry that enables or disables the Microsoft User Experience Virtualization (UE-V) synchronization of Windows® 8 apps.
If you do not specify the *Computer* or *CurrentComputerUser* parameter, the cmdlet clears the setting for the package families for the current user.

## EXAMPLES

### Example 1: Remove Windows 8 apps
```
PS C:\>Clear-UevAppxPackage -Computer -All
```

This command removes all Windows 8 apps from the Windows 8 app list on the computer.

## PARAMETERS

### -All
Indicates that the cmdlet clears all of the computer or user settings for the package families that you specify.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAllComputerTemplates, ParameterSetAllUserTemplates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Computer
Indicates that the cmdlet clears the setting for package families that you specify for all users on the computer.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer, ParameterSetAllComputerTemplates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurrentComputerUser
Indicates that the cmdlet clears the setting for the package families that you specify for the current user on the computer.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetUser, ParameterSetAllUserTemplates
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageFamilyName
Specifies an array of names of package families.
The cmdlet clears the setting for the package families of Windows 8 apps that you specify.

```yaml
Type: String[]
Parameter Sets: ParameterSetUser, ParameterSetComputer
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-UevAppxPackage](./Disable-UevAppxPackage.md)

[Enable-UevAppxPackage](./Enable-UevAppxPackage.md)

[Get-UevAppxPackage](./Get-UevAppxPackage.md)

