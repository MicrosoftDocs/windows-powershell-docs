---
author: Kateyanne
description: 
external help file: Microsoft.Windows.StartScreen.Commands.dll-Help.xml
manager: jasgro
Module Name: StartScreen
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/startscreen/export-startlayout?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-StartLayout
---

# Export-StartLayout

## SYNOPSIS
Exports the layout of the Start screen.

## SYNTAX

### Non-literal
```
Export-StartLayout [[-As] <AsFileType>] [-Path] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Literal
```
Export-StartLayout [[-As] <AsFileType>] [-LiteralPath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-StartLayout** cmdlet exports the layout of the Start screen of the current user.
You can export layout as an .xml file to verify the layout, or you can export layout as a .bin file to modify the layout of an existing Windows image.
Specify the appropriate file name extension, .bin or .xml, in the name of the file.
To modify the layout of a Windows image, export the layout as a .bin file, and then import it into a Windows image by using the Import-StartLayout cmdlet.

## EXAMPLES

### Example 1: Export the layout as a .bin file
```
PS C:\> Export-StartLayout -Path "C:\Layouts\Marketing.bin" -As BIN
```

This command exports the layout of the Start screen to a file named Marketing.bin in the C:\Layouts folder.
The command specifies a value of BIN for the **As** parameter, so the cmdlet creates a .bin file.

## PARAMETERS

### -As
Specifies a file type to export.
The acceptable values for this parameter are:

- BIN.
Export as a .bin file. 
- XML.
Export as an .xml file. 

The default value is BIN.

```yaml
Type: AsFileType
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: BIN
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

### -LiteralPath
Specifies a literal path to a layout file.
Include the file name extension, .bin or .xml.
This parameter does not accept the wildcard character (*).
If the path includes an escape character (\\), enclose the string in single quotes (').

```yaml
Type: String
Parameter Sets: Literal
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies an absolute path to a layout file.
Include the file name extension, .bin or .xml.

```yaml
Type: String
Parameter Sets: Non-literal
Aliases: 

Required: True
Position: 1
Default value: Current Location
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

### Enum
You can specify the following file formats: 

- BIN.
Export as a .bin file. 
- XML.
Export as an .xml file.

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-StartLayout](./Import-StartLayout.md)

