---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Medv.Administration.Commands.WorkspacePackager.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Export-MedvWorkspace
---

# Export-MedvWorkspace

## SYNOPSIS
Creates Windows Installer file and related files.

## SYNTAX

```
Export-MedvWorkspace [-Path] <String> [-InputObject] <MedvWorkspace> [-Overwrite [<SwitchParameter>]] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]] [<CommonParameters>]
```

## DESCRIPTION
The **Export-MedvWorkspace** cmdlet creates a Windows Installer file and related files.
Specify a **MedvWorkspace** object that contains the package details.

## EXAMPLES

### Example 1: Create a workspace package
```
C:\PS>New-MedvWorkspace -WorkspaceName "XPCompat" -VhdfilePath "C:\xpImage.vhd" -SettingsFilePath "XPCompat.reg" | Export-MedvWorkspace -Path "XPCompat.msi"
```

This command uses the **New-MedvWorkspace** to create an object that contains all the information necessary to create a MED-V workspace.
The command passes the result to the current cmdlet.
That cmdlet creates a workspace package that includes files necessary to install a workspace package with the name XPCompat that uses the settings in the specified registry file.

## PARAMETERS

### -InputObject
Specifies a **MedvWorkspace** object.
To obtain a **MedvWorkspace** object, use the **New-MedvWorkspace** cmdlet.

```yaml
Type: MedvWorkspace
Parameter Sets: (All)
Aliases: i

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Overwrite
Indicates that this cmdlet overwrites an existing MED-V workspace package.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the full path of the Windows Installer file to generate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: p

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
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

### Microsoft.Medv.Administration.Commands.MedvWorkspace
This cmdlet accepts a **MedvWorkspace** object.
A **MedvWorkspace** object contains the information and location of all files needed to make the workspace setup files.

## OUTPUTS

## NOTES

## RELATED LINKS

[New-MedvWorkspace](./New-MedvWorkspace.md)


