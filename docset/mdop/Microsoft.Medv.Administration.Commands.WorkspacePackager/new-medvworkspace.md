---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Medv.Administration.Commands.WorkspacePackager.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: New-MedvWorkspace
---

# New-MedvWorkspace

## SYNOPSIS
Creates an object that contains the properties for a workspace Windows Installer file.

## SYNTAX

```
New-MedvWorkspace [-WorkspaceName] <String> [-VhdFilePath] <String> [-SettingsFilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-MedvWorkspace** cmdlet creates an object that contains the properties needed to create a workspace Windows Installer file.
You can use the **Export-MedvWorkspace** cmdlet to create the setup files necessary to deploy a workspace.

## EXAMPLES

### Example 1: Create a workspace configuration object
```
C:\PS>New-MedvWorkspace -WorkspaceName "XPCompat" -VhdfilePath "C:\xpImage.vhd" -SettingsFilePath "XPCompat.reg"
```

This command creates an object that contains all the information necessary to create a MED-V workspace named XPCompat.
The command specifies a .vhd file and registry settings.

### Example 2: Create a workspace package
```
C:\PS>New-MedvWorkspace -WorkspaceName "XPCompat" -VhdfilePath "C:\xpImage.vhd" -SettingsFilePath "XPCompat.reg" | Export-MedvWorkspace -Path "XPCompat.msi"
```

This command creates an object that contains all the information necessary to create a MED-V workspace.
The command passes the result to the **Export-MedvWorkspace** cmdlet.
That cmdlet creates a workspace package.

## PARAMETERS

### -SettingsFilePath
Specifies the full path of a file that has the .reg file name extension.
That file contains the MED-V settings for the MED-V workspace.
This file is packaged with the setup files.
The MED-V workspace packager imports these settings into the registry of the target computer.
You can generate this file by using the **New-MedvConfiguration** and **Export-MedvConfiguration** cmdlets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: s, sfp, settings

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VhdFilePath
Specifies the full path of the virtual hard drive (.vhd) file.
This file is converted to a MED-V file and stored with the Windows Installer file.
When deployed, the Windows Installer file must be in the same folder as the newly created MED-V file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: vhd, vfp

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Specifies the name of the MED-V workspace.
The name of the MED-V workspace is displayed to end users.

```yaml
Type: String
Parameter Sets: (All)
Aliases: w, wn, ws, n, name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-MedvWorkspace](./Export-MedvWorkspace.md)


