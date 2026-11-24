---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
Module Name: MultiPointVdi
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipointvdi/open-wmsvirtualdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Open-WmsVirtualDesktop
---

# Open-WmsVirtualDesktop

## SYNOPSIS
Opens a window connected to a virtual desktop template.

## SYNTAX

```
Open-WmsVirtualDesktop -TemplateVirtualMachineGuid <String> [-Domain <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Open-WmsVirtualDesktop** cmdlet opens a window connected to the specified virtual desktop template.
This enables you to customize the virtual desktop template in order to customize virtual desktops that you create.

## EXAMPLES

### Example 1: Open a window to a virtual desktop template
```
PS C:\> Open-WmsVirtualDesktop -TemplateVirtualMachineGuid "53F56307-B6BF-11D0-94F2-00A0C91EFB8B"
```

This command opens a window that is connected to the virtual desktop template with the ID 53F56307-B6BF-11D0-94F2-00A0C91EFB8B.

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

### -Domain
Specifies the name of the Active Directory domain that contains the virtual desktop template.

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

### -TemplateVirtualMachineGuid
Specifies the Hyper-V virtual machine ID of the virtual desktop template.

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

[New-WmsVirtualDesktop](./New-WmsVirtualDesktop.md)

