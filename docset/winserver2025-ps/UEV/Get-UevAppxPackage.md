---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/get-uevappxpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UevAppxPackage
---

# Get-UevAppxPackage

## SYNOPSIS
Gets a list of Windows 8 apps and synchronization status.

## SYNTAX

### ParameterSetNoParameter (Default)
```
Get-UevAppxPackage [<CommonParameters>]
```

### ParameterSetComputer
```
Get-UevAppxPackage [-Computer] [<CommonParameters>]
```

### ParameterSetUser
```
Get-UevAppxPackage [-CurrentComputerUser] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UevAppxPackage** cmdlet gets a list of Windows® 8 apps and the Microsoft User Experience Virtualization (UE-V) synchronization status for the apps.
If you do not specify the **Computer** or **CurrentComputerUser** parameters, the cmdlet gets the list of Windows 8 apps for the current user.

## EXAMPLES

### Example 1: Get the list of Windows 8 apps
```
PS C:\>Get-UevAppxPackage -CurrentComputerUser
```

This command gets the list of Windows 8 apps that are configured for the current user.

## PARAMETERS

### -Computer
Indicates that the cmdlet gets the Windows 8 apps and UE-V synchronization status for all users on the computer.

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

### -CurrentComputerUser
Indicates that the cmdlet gets the Windows 8 apps and UE-V synchronization status for the current user on the computer.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetUser
Aliases:

Required: True
Position: Named
Default value: None
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

[Disable-UevAppxPackage](./Disable-UevAppxPackage.md)

[Enable-UevAppxPackage](./Enable-UevAppxPackage.md)

