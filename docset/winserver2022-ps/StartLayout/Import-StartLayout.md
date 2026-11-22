---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.StartLayout.Commands.dll-Help.xml
Module Name: StartLayout
ms.date: 09/13/2018
online version: https://learn.microsoft.com/powershell/module/startlayout/import-startlayout?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-StartLayout
---

# Import-StartLayout

## SYNOPSIS
Imports the layout of the Start into a mounted Windows image.

## SYNTAX

### Path
```powershell
Import-StartLayout [-LayoutPath] <String> [-MountPath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath
```powershell
Import-StartLayout -LayoutLiteralPath <String> -MountLiteralPath <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-StartLayout** cmdlet imports the specified layout of Start into a mounted Windows image.
When you import a layout, it replaces the existing layout of Start for the default user profile. When the Windows image is booted, new users will receive the imported layout at sign-in. New users will be able to customize their default layout, but not the layout for the default user profile.

Before you use this cmdlet, mount the Windows image file to import the layout into.

You must have administrator rights to import a layout.

In Windows 10, the Export-StartLayout cmdlet exports layouts as .xml files, and the **Import-StartLayout** cmdlet imports only .xml files.

> [!CAUTION]
> The Import-StartLayout cmdlet is deprecated in Windows 11. It has no effect on either Start or Taskbar layout. To configure the Start layout in Windows 11, see [Customize the Windows 11 Start layout](https://learn.microsoft.com/en-us/windows-hardware/customize/desktop/customize-the-windows-11-start-menu). To configure Taskbar layout in Windows 11, see [Customize the Taskbar](https://learn.microsoft.com/en-us/windows-hardware/customize/desktop/customize-the-windows-11-taskbar).
## EXAMPLES

### Example 1: Import a layout into a Windows image
```
PS C:\> Import-StartLayout -LayoutPath "Layout.xml" -MountPath "C:\"
```

This command imports a layout of the Start screen into a Windows image.

### Example 2: Validate the layout file and Windows image
```
PS C:\> Import-StartLayout -LayoutPath "Layout.xml" -MountPath " C:\" -WhatIf
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
Position: Named
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
Default value: None
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPath
Specifies the path where you mounted the .wim file and specifies the local appdata folder for the default user.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: 2
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-StartLayout](./Export-StartLayout.md)

[Start Layout Cmdlets](./startlayout.md)

