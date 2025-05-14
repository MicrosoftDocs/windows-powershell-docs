---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
Module Name: MultiPointVdi
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipointvdi/get-wmsvirtualdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsVirtualDesktop
---

# Get-WmsVirtualDesktop

## SYNOPSIS
Gets a virtual desktop.

## SYNTAX

```
Get-WmsVirtualDesktop [-VirtualMachineName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsVirtualDesktop** cmdlet gets the specified virtual desktop or all virtual desktops if you don't specify the *VirtualMachineName* parameter.

## EXAMPLES

### Example 1: Get a virtual desktop by name
```
PS C:\> Get-WmsVirtualDesktop -VirtualMachineName "MyDesktop"
```

This command gets the virtual desktop named MyDesktop.

## PARAMETERS

### -VirtualMachineName
Specifies the name of the virtual desktop to get.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Import-WmsVirtualDesktop](./Import-WmsVirtualDesktop.md)

[New-WmsVirtualDesktop](./New-WmsVirtualDesktop.md)

[Open-WmsVirtualDesktop](./Open-WmsVirtualDesktop.md)

