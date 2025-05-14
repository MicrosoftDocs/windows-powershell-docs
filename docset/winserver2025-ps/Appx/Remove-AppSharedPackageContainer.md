---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/remove-appsharedpackagecontainer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AppSharedPackageContainer
---

# Remove-AppSharedPackageContainer

## SYNOPSIS
Removes the shared package container.

## SYNTAX

```
Remove-AppSharedPackageContainer [-Name] <String> [-ForceApplicationShutdown] [-AllUsers]
 [<CommonParameters>]
```

## DESCRIPTION

The cmdlet removes the shared package container definition for the particular user.

## EXAMPLES

### Example 1

```powershell
Remove-AppSharedPackageContainer -Name ContosoTestContainer
```

This command removes the shared package container definition with the name `ContosoTestContainer`.

## PARAMETERS

### -AllUsers

Unsupported. Will result in `-AllUsers functionality is not yet implemented` error.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceApplicationShutdown

Closes all packages in the Shared Package Container.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

The name of the container.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
