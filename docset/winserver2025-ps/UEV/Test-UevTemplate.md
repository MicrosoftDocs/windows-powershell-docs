---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/test-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-UevTemplate
---

# Test-UevTemplate

## SYNOPSIS
Verifies whether a template complies with the schema for UE-V.

## SYNTAX

### Path (Default)
```
Test-UevTemplate [-Path] <String[]> [<CommonParameters>]
```

### LiteralPath
```
Test-UevTemplate -LiteralPath <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Test-UevTemplate** cmdlet verifies whether a settings location template complies with the XML schema for Microsoft User Experience Virtualization (UE-V).

## EXAMPLES

### Example 1: Test a file
```
PS C:\> Test-UevTemplate -Path "MicrosoftWordpad.xml" | Format-Table -AutoSize
Path                                                                                     Status Message
----                                                                                     ------ -------
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftWordpad.xml Valid  The template is valid.
```

This command tests whether the specified file is a valid settings location template.
The command passes the results to the **Format-Table** cmdlet by using the pipeline operator.
For more information, type `Get-Help Format-Table`.

### Example 2: Test several files
```
PS C:\> Test-UevTemplate -Path "*Microsoft*.xml" | Format-Table -AutoSize
Path                                                                                               Status Message
----                                                                                               ------ -------
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftCalculator.xml        Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftInternetExplorer9.xml Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftLync2010.xml          Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftNotepad.xml           Valid  The template is valid.
```

This command tests whether several files are valid settings location templates.
The command checks all .xml files that have names that contain the specified string.
The command passes the results to **Format-Table** by using the pipeline operator.

### Example 3: Test a file specified by its literal path
```
PS C:\> Test-UevTemplate -LiteralPath "MicrosoftWordpad.xml" | Format-Table -AutoSize
Path                                                                                     Status Message
----                                                                                     ------ -------
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftWordpad.xml Valid  The template is valid.
```

This command tests whether the specified file is a valid settings location template file.
The command passes the results to **Format-Table** by using the pipeline operator.

### Example 4: Test all the files in the current directory by using the pipeline
```
PS C:\> Test-UevTemplate -Path "*.xml" | Format-Table -AutoSize
Path                                                                                               Status Message
----                                                                                               ------ -------
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftCalculator.xml        Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftInternetExplorer9.xml Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftLync2010.xml          Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftNotepad.xml           Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftOffice2010.xml        Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftVisualStudio2010.xml  Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftWindows7.xml          Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftWindows8.xml          Valid  The template is valid.
C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftWordpad.xml           Valid  The template is valid.
```

This command uses a wildcard to test if each file is a settings location template, and then passes the results to **Format-Table** by using the pipeline operator.

## PARAMETERS

### -LiteralPath
Specifies an array of literal file paths.
The cmdlet validates the settings location templates that have the literal paths that you specify.

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
The cmdlet validates the settings location templates that have the paths that you specify.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string[]
An array of paths to settings location templates.

## OUTPUTS

### Microsoft.UEV.Commands.TestTemplateResult
This cmdlet generates a **TestTemplateResult** object that contains the validation result for a settings location template.

## NOTES

## RELATED LINKS

[Disable-UevTemplate](./Disable-UevTemplate.md)

[Enable-UevTemplate](./Enable-UevTemplate.md)

[Get-UevTemplate](./Get-UevTemplate.md)

[Register-UevTemplate](./Register-UevTemplate.md)

[Unregister-UevTemplate](./Unregister-UevTemplate.md)

[Update-UevTemplate](./Update-UevTemplate.md)

