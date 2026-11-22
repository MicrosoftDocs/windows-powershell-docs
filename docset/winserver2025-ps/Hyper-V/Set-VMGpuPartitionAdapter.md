---
description: Assigns a partition of a GPU to a virtual machine.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmgpupartitionadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMGpuPartitionAdapter
---

# Set-VMGpuPartitionAdapter

## SYNOPSIS
Assigns a partition of a GPU to a virtual machine.

## SYNTAX

### VMName (Default)

```
Set-VMGpuPartitionAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-Passthru] [-AdapterId <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject

```
Set-VMGpuPartitionAdapter [-VM] <VirtualMachine[]> [-Passthru] [-AdapterId <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object

```
Set-VMGpuPartitionAdapter [-VMGpuPartitionAdapter] <VMGpuPartitionAdapter[]> [-Passthru]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-VMGpuPartitionAdapter` cmdlet assigns a partition of a GPU to a virtual machine. Running
the command against a virtual machine assigns a full partition. Additional parameters exist to
assign more specific options to a VM.

## EXAMPLES

### Example 1

```powershell
$vm = Get-VM "Test"
Set-VMGpuPartitionAdapter -VM $vm
```

This example assign a partition to a VM passing a VM object.

## PARAMETERS

### -AdapterId

A VM's GPU partition identification number used to display the GPU information assigned to a VM.

```yaml
Type: String
Parameter Sets: VMName, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies one or more Hyper-V hosts on the virtual network adapters are to be retrieved. NetBIOS
names, IP addresses, and fully qualified domain names are allowed. The default is the local
computer. Use localhost or a dot (`.`) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies one or more user accounts that have permission to perform this action. The default is the
current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionCompute

The maximum number of compute assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionDecode

The maximum number of decoders assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionEncode

The maximum number of encoders assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionVRAM

The maximum VRAM in bytes supported by the host GPU. This is defined by the manufacturer's driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionCompute

The minimum number of compute assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionDecode

The minimum number of decoders assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionEncode

The minimum number of encoders assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionVRAM

The minimum VRAM in bytes supported by the host GPU. This is defined by the manufacturer's driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionCompute

The optimal number of compute assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionDecode

The optimal number of decoders assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionEncode

The optimal number of encoders assigned by the host GPU. This is defined by the manufacturer's
driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionVRAM

The optimal VRAM in bytes supported by the host GPU. This is defined by the manufacturer's driver.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru

Returns an object for each process that the cmdlet started.

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

### -VM

Specifies the virtual machine whose virtual network adapters are to be retrieved. The asterisk (`*`)
is the wildcard. If it is specified the cmdlet returns virtual network adapters from every virtual
machine in the system.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMGpuPartitionAdapter

GPU partition object obtained from `Get-VMGpuPartitionAdapter`.

```yaml
Type: VMGpuPartitionAdapter[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName

Specifies the name of the virtual machine whose network adapters are to be configured.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter

## NOTES

## RELATED LINKS

[Add-VMGpuPartitionAdapter](add-vmgpupartitionadapter.md)

[Get-VMGpuPartitionAdapter](get-vmgpupartitionadapter.md)

[Remove-VMGpuPartitionAdapter](remove-vmgpupartitionadapter.md)
