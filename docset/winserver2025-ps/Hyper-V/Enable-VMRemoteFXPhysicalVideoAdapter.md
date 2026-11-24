---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/enable-vmremotefxphysicalvideoadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-VMRemoteFXPhysicalVideoAdapter
---

# Enable-VMRemoteFXPhysicalVideoAdapter

## SYNOPSIS
Enables one or more RemoteFX physical video adapters for use with RemoteFX-enabled virtual machines.

## SYNTAX

### GPUByName (Default)

```
Enable-VMRemoteFXPhysicalVideoAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-Name] <String[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### GPUByObject

```
Enable-VMRemoteFXPhysicalVideoAdapter [-GPU] <VMRemoteFXPhysicalVideoAdapter[]> [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Enable-VMRemoteFXPhysicalVideoAdapter** cmdlet enables one or more RemoteFX physical video
adapters to be used with RemoteFX-enabled virtual machines.

## EXAMPLES

### Code Example Title

```powershell
Get-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia* | Enable-VMRemoteFXPhysicalVideoAdapter
```

Enables all RemoteFX physical video adapters which include the sequence "Nvidia" in their name.

## PARAMETERS

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: GPUByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies one or more Hyper-V hosts on which the RemoteFX physical video adapters are to be enabled.
NetBIOS names, IP addresses, and fully qualified domain names are allowable. The default is the
local computer. Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: GPUByName
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

### -Credential

Specifies one or more user accounts that have permission to perform this action. The default is the
current user.

```yaml
Type: PSCredential[]
Parameter Sets: GPUByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPU

Specifies the RemoteFX physical video adapters to be enabled.

```yaml
Type: VMRemoteFXPhysicalVideoAdapter[]
Parameter Sets: GPUByObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies an array of names of adapters. The cmdlet enables the RemoteFX physical video adapters
that you specify.

```yaml
Type: String[]
Parameter Sets: GPUByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru

Specifies that one or more **Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter** objects
are to be passed through to the pipeline representing the RemoteFX physical video adapters to be
enabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter[]

### System.String[]

## OUTPUTS

### None

By default, this cmdlet doesn't return any output.

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter

What you use the **PassThru** parameter, the cmdlet returns
**Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter** objects.

## NOTES

## RELATED LINKS
