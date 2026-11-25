---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/add-appsharedpackagecontainer?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AppSharedPackageContainer
---

# Add-AppSharedPackageContainer

## SYNOPSIS
Deploys the shared package container definition.

## SYNTAX

```
Add-AppSharedPackageContainer [-Path] <String> [-ForceApplicationShutdown] [-Merge]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Add-AppSharedPackageContainer` cmdlet deploys the shared package container definition for the
particular user.

## EXAMPLES

### Example 1

```powershell
Add-AppSharedPackageContainer -Path C:\MyFolder\ContosoTestContainer.xml
```

This command deploys the definition described in the ContosoTestContainer file.

## PARAMETERS

### -Force

Replaces an existing container of the same name with the newly created container's definition for
the target users.

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

Closes all packages currently running in the Shared Package Container.

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

### -Merge

Merges a new container's definition into an existing container definition of the same name for
target users.

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

### -Path

Path to the XML definition file.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
