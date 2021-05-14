---
external help file: Microsoft.Windows.StartScreen.Commands.dll-Help.xml
Module Name: StartScreen
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/startscreen/import-startlayout?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-StartLayout
---

# Import-StartLayout

## SYNOPSIS
Imports the layout of the Start screen into a mounted Windows image.

## SYNTAX

### Path
```
Import-StartLayout [-LayoutPath] <String> [-MountPath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath
```
Import-StartLayout [-LayoutLiteralPath] <String> [-MountLiteralPath] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-StartLayout** cmdlet imports the layout of the Start screen into a mounted Windows image.
When you import a layout, it replaces the existing layout of the Start screen.
Before you use this cmdlet, mount the Windows image file to import the layout into.

Use the Export-StartLayout cmdlet to create a .bin file, and then use this cmdlet to import that file.
You must have administrator rights to import a layout.

The Export-StartLayout cmdlet also exports layouts as .xml files, but this cmdlet imports only .bin files.

## EXAMPLES

### Example 1: Import a layout into a Windows image
```
PS C:\> Import-StartLayout -LayoutPath "Layout.bin" -MountPath "E:\MountedImage\"
```

This command imports a layout of the Start screen into a Windows image.

### Example 2: Validate the layout file and Windows image
```
PS C:\> Import-StartLayout -LayoutPath "Layout.bin" -MountPath "E:\MountedImage" -WhatIf
```

This command validates the layout file and the Windows image by using the **WhatIf** parameter.
Besides that parameter, the command is the same as the previous example, but this command makes no changes.

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

### -LayoutLiteralPath
Specifies a literal path to a layout file.
This parameter does not accept the wildcard character (*).
If the path includes an escape character (\\), enclose the string in single quotes (').

```yaml
Type: String
Parameter Sets: LiteralPath
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LayoutPath
Specifies a path to a layout file.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: 1
Default value: Null
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountLiteralPath
Specifies the literal path where you mounted the .wim file.
This parameter does not accept the wildcard character (*).
If the path includes an escape character (\\), enclose the string in single quotes (').

```yaml
Type: String
Parameter Sets: LiteralPath
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPath
Specifies the path where you mounted the .wim file.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: 2
Default value: Null
Accept pipeline input: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-StartLayout](./Export-StartLayout.md)

