---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/get-appsharedpackagecontainer?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppSharedPackageContainer
---

# Get-AppSharedPackageContainer

## SYNOPSIS
Gets information about the shared package container.

## SYNTAX

```
Get-AppSharedPackageContainer [[-Name] <String>] [[-Id] <String>] [-AllUsers]
 [<CommonParameters>]
```

## DESCRIPTION

The cmdlet shows information about any shared package container. In particular, it shows what
packages are inside the shared package container.

## EXAMPLES

### Example 1

```powershell
Get-AppSharedPackageContainer -Name Contoso*
```

```output
Name               : ContosoTestContainer
Id                 : ContosoTestContainer_1
PackageFamilyNames : {Contoso.SpellCheckPlugin.1.0.0.0_7pneu3d8sswe, Notepad++.2.0.0.1_ohjis898f1}

Name               : ContosoTestContainer
Id                 : ContosoTestContainer_2
PackageFamilyNames : {Contoso.SpellCheckPlugin2.1.0.0.0_7pneu3d8sswe, Notepad++.2.0.0.1_ohjis898f1}
```

This command shows the packages in any shared package container that has a prefix of Contoso.

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

### -Id

Id of the container. Can be acquired by running `Get-AppSharedPackageContainer`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

The name of the container.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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
