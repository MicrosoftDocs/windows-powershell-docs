---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/export-uevpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-UevPackage
---

# Export-UevPackage

## SYNOPSIS
Exports the settings stored in a settings package.

## SYNTAX

### Path (Default)
```
Export-UevPackage [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath
```
Export-UevPackage -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-UevPackage** cmdlet exports the settings that are stored in a settings package to an XML file.

## EXAMPLES

### Example 1: Export a UE-V package
```
PS C:\> Export-UevPackage -Path "MicrosoftCalculator6.pkgx"
<SettingsDocument>
<registry>
<Setting Type="VT_BINARY" Name="registry://HKCU\Software\Microsoft\Calc\Window_Placement" Action="Update">LAAAAAAAAAABAAAA/////////////////////60AAABQAAAAVAIAANQBAAA=</Setting>
<Setting Type="VT_DWORD" Name="registry://HKCU\Software\Microsoft\Calc\layout" Action="Update">2</Setting>
</registry>
</SettingsDocument>
```

This command exports a settings package file for Microsoft calculator by using the *Path* parameter.

### Example 2: Export a UE-V package by name
```
PS C:\> Export-UevPackage -Path "*calc*.pkgx"


<SettingsDocument>
<registry>
<Setting Type="VT_BINARY" Name="registry://HKCU\Software\Microsoft\Calc\Window_Placement" Action="Update">LAAAAAAAAAABAAAA/////////////////////60AAABQAAAAVAIAANQBAAA=</Setting>
<Setting Type="VT_DWORD" Name="registry://HKCU\Software\Microsoft\Calc\layout" Action="Update">2</Setting>
</registry>
</SettingsDocument>
```

This command exports a settings package file for Microsoft calculator by using wildcard characters in the file name.

### Example 3: Export a UE-V package by path
```
PS C:\> Export-UevPackage -LiteralPath "MicrosoftCalculator6.pkgx"
<SettingsDocument>
<registry>
<Setting Type="VT_BINARY" Name="registry://HKCU\Software\Microsoft\Calc\Window_Placement" Action="Update">LAAAAAAAAAABAAAA/////////////////////60AAABQAAAAVAIAANQBAAA=</Setting>
<Setting Type="VT_DWORD" Name="registry://HKCU\Software\Microsoft\Calc\layout" Action="Update">2</Setting>
</registry>
</SettingsDocument>
```

This command exports a settings package file for Microsoft calculator.
The example does not use wildcard characters in the path.

## PARAMETERS

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

### -LiteralPath
Specifies an array of literal file paths.
The cmdlet exports the settings location templates that have the literal paths that you specify.

```yaml
Type: String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies an array of file paths.
The cmdlet exports the settings location templates that have the paths you specify.
Use wildcards to specify multiple files.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### string[]
A collection of paths to the settings packages.

## OUTPUTS

### System.String
This cmdlet generates XML text that describes the settings stored in the specified settings package.

## NOTES

## RELATED LINKS

