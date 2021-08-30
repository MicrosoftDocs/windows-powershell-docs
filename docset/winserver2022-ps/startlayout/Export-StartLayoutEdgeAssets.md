---
description: The Export-StartLayoutEdgeAssets cmdlet exports secondary tiles for Microsoft Edge that display a custom image.
external help file: Microsoft.Windows.StartLayout.Commands.dll-Help.xml
Module Name: StartLayout
ms.date: 09/03/2021
online version: https://docs.microsoft.com/powershell/module/startlayout/export-startlayoutedgeassets?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-StartLayoutEdgeAssets

## SYNOPSIS
Exports secondary tiles for Microsoft Edge that display a custom image.

## SYNTAX

### Non-literal
```
Export-StartLayoutEdgeAssets [-Path] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Literal
```
Export-StartLayoutEdgeAssets -LiteralPath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-StartLayoutEdgeAssets** cmdlet exports secondary tiles for Microsoft Edge that display a custom image.
Use [Export-StartLayout](./Export-StartLayout.md) and [Import-StartLayout](./Import-StartLayout.md) along with the current cmdlet to import the assets.

## EXAMPLES

### Example 1: Export assets.
```powershell
Export-StartLayoutEdgeAssets -Path "C:\Layouts\assets.xml"
```

This example exports the assets to the file `assets.xml` in the C:\Layouts folder.
This cmdlet does not append `.xml` to a file name.

## PARAMETERS

### -LiteralPath
Specifies a literal path for an asset file.
Include the `.xml` file name extension.
This parameter does not accept the wildcard character (*).
If the path includes an escape character (\\), enclose the string in single quotes (').

```yaml
Type: String
Parameter Sets: Literal
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies an absolute path for an asset file.
Include the `.xml` file name extension.
This parameter does not accept the wildcard character (*).

```yaml
Type: String
Parameter Sets: Non-literal
Aliases:

Required: True
Position: 1
Default value: None
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Export-StartLayout](./Export-StartLayout.md)

[Get-StartApps](Get-StartApps.md)

[Import-StartLayout](./Import-StartLayout.md)
