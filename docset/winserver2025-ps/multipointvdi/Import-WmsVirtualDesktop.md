---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
Module Name: MultiPointVdi
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipointvdi/import-wmsvirtualdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-WmsVirtualDesktop
---

# Import-WmsVirtualDesktop

## SYNOPSIS
Creates a virtual desktop template hard disk image.

## SYNTAX

```
Import-WmsVirtualDesktop -InputFilePath <String> [-VhdLocation <String>] -TemplatePrefix <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-WmsVirtualDesktop** cmdlet creates the Windows MultiPoint Services (WMS) virtual switch if it doesn't already exist, shuts down any existing MultiPoint station virtual machines that may be running, and creates a template virtual machine hard disk (.vhd) from the specified Windows image.

## EXAMPLES

### Example 1: Import a template
```
PS C:\> Import-WmsVirtualDesktop -InputFilePath "C:\Images\Windows10Enterprise.iso" -TemplatePrefix "MyVdiImage" -VhdLocation "C:\MultiPointVhdImages"
```

This command creates a virtual machine template named MyVdiImage that installs the guest operating system from C:\images\Windows10Enterprise.iso, and stores the resulting .vhd file in the folder C:\MultiPointVhdImages.

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

### -InputFilePath
Specifies the full path of the input file to use for the virtual desktop template.
Valid file types are .wim, .iso, or .vhd that contains the version of Windows to use as the guest operating system.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplatePrefix
Specifies the prefix to use for the name of the virtual machine template.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdLocation
Specifies the path in which to store the template and station .vhd files.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WmsVirtualDesktop](./Get-WmsVirtualDesktop.md)

[New-WmsVirtualDesktop](./New-WmsVirtualDesktop.md)

[Open-WmsVirtualDesktop](./Open-WmsVirtualDesktop.md)

