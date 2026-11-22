---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMTemplate
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmtemplate/initialize-vmshieldinghelpervhd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-VMShieldingHelperVHD
---

# Initialize-VMShieldingHelperVHD

## SYNOPSIS
Initializes a VHD for use as a shielding utility disk in a guarded fabric.

## SYNTAX

```
Initialize-VMShieldingHelperVHD -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Protect-TemplateDisk** cmdlet initializes a virtual hard disk (VHD) for use as a shielding utility disk in a guarded fabric.

Utility VHDs contain the software needed to shield an existing VM on a guarded fabric.
A supported operating system must be installed on the disk before initializing it as a shielding helper VHD.

For more information about preparing a shielding helper VHD, see Shielded VMs - Hosting service provider prepares a VM Shielding Helper VHDhttps://technet.microsoft.com/en-us/windows-server-docs/security/guarded-fabric-shielded-vm/guarded-fabric-vm-shielding-helper-vhd at https://go.microsoft.com/fwlink/?linkid=832557.

## EXAMPLES

### Example 1: Initialize a virtual hard disk
```
PS C:\>Initialize-VMShieldingHelperVHD -Path "C:\temp\ShieldedVMUtility.vhdx"
```

## PARAMETERS

### -Path
Specifies the path of the .vhdx file to initialize.

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

[Protect-TemplateDisk](./Protect-TemplateDisk.md)

