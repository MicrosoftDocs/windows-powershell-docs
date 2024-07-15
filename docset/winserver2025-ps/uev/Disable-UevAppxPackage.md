---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/disable-uevappxpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-UevAppxPackage
---

# Disable-UevAppxPackage

## SYNOPSIS
Disables UE-V synchronization of Windows 8 apps.

## SYNTAX

### ParameterSetUser (Default)
```
Disable-UevAppxPackage [-CurrentComputerUser] [-PackageFamilyName] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParameterSetComputer
```
Disable-UevAppxPackage [-Computer] [-PackageFamilyName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-UevAppxPackage** cmdlet disables Microsoft User Experience Virtualization (UE-V) synchronization of Windows® 8 apps.
The cmdlet adds a setting to the computer or user sections of the registry that disables the package family names of Windows 8 apps that you specify.
If you do not specify the *Computer* or *CurrentComputerUser* parameters, the cmdlet disables the package family names of Windows 8 apps for the current user.

## EXAMPLES

### Example 1: Disable synchronization of a Windows 8 app
```
PS C:\>Disable-UevAppxPackage -Computer -PackageFamilyName "Microsoft.BingFinance"
```

This command disables synchronization of the Bing Finance app for all users on the computer.

## PARAMETERS

### -Computer
Indicates that the cmdlet disables the Windows 8 apps that you specify for all users on the computer.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
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
Indicates that the cmdlet disables the Windows 8 apps that you specify for the current user only.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageFamilyName
Specifies an array of package families.
The cmdlet disables the package families of Windows 8 apps that you specify.

```yaml
Type: String[]
Parameter Sets: (All)
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

[Clear-UevAppxPackage](./Clear-UevAppxPackage.md)

[Enable-UevAppxPackage](./Enable-UevAppxPackage.md)

[Get-UevAppxPackage](./Get-UevAppxPackage.md)

