---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
Module Name: MultiPointVdi
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipointvdi/new-wmsvirtualdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WmsVirtualDesktop
---

# New-WmsVirtualDesktop

## SYNOPSIS
Creates a virtual desktop.

## SYNTAX

### CreateVirtualDesktopById
```
New-WmsVirtualDesktop [-StationId] <UInt32[]> -InputFilePath <String> [-VhdLocation <String>]
 -TemplatePrefix <String> [-Domain <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateAllVirtualDesktops
```
New-WmsVirtualDesktop [-All] -InputFilePath <String> [-VhdLocation <String>] -TemplatePrefix <String>
 [-Domain <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-WmsVirtualDesktop** cmdlet creates a virtual desktop from the specified virtual desktop template for a specified MultiPoint station or all stations, and replaces any existing stations in the process.

## EXAMPLES

### Example 1: Create a virtual desktop for all stations on a computer
```
PS C:\> New-WmsVirtualDesktop -All -InputFilePath "C:\Images\Windows10Enterprise.iso" -TemplatePrefix "MyVdiImage" -VhdLocation "C:\MultiPointVhdImages"
```

This command creates a virtual desktop from the template in C:\Images\Windows10Enterprise.iso for all of the stations on a computer.

## PARAMETERS

### -All
Indicates that this operation creates a virtual desktop for all stations.

```yaml
Type: SwitchParameter
Parameter Sets: CreateAllVirtualDesktops
Aliases:

Required: False
Position: Named
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the name of the Active Directory domain to contain the virtual desktop.

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

### -StationId
Specifies an array of station IDs for which to create a virtual desktop.

```yaml
Type: UInt32[]
Parameter Sets: CreateVirtualDesktopById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the path to store the template and station .vhd files.

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

[Import-WmsVirtualDesktop](./Import-WmsVirtualDesktop.md)

[Open-WmsVirtualDesktop](./Open-WmsVirtualDesktop.md)

