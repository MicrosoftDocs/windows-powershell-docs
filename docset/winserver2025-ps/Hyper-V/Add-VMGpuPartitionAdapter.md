---
description: Adds a GPU partition adapter to a virtual machine.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmgpupartitionadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMGpuPartitionAdapter
---

# Add-VMGpuPartitionAdapter

## SYNOPSIS
Adds a GPU partition adapter to a virtual machine.

## SYNTAX

### VMName (Default)

```
Add-VMGpuPartitionAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-Passthru] [-InstancePath <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject

```
Add-VMGpuPartitionAdapter [-VM] <VirtualMachine[]> [-Passthru] [-InstancePath <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Add-VMGpuPartitionAdapter` cmdlet adds a GPU partition adapter to a virtual machine. With no
parameter, it assigns a full partition from an assignable GPU to a VM.

## EXAMPLES

### Example 1

```powershell
$vm = Get-VM -Name "TestVM"
Add-VMGpuPartitionAdapter -VM $vm
```

This example assigns a partition to a specific VM object.

### Example 2

```powershell
$vm = Get-VM -Name "TestVM"
Add-VMGpuPartitionAdapter -VM $vm -InstancePath "GPUInstancePath"
```

This example assigns a partition from a specific GPU to a VM where the instance path is the GPU
device ID name on the host.

## PARAMETERS

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

Specifies one or more Hyper-V hosts from which virtual machines are to be retrieved. NetBIOS names,
IP addresses, and fully qualified domain names are allowable. The default is the local computer.
Use localhost or a dot (`.`) to specify the local computer explicitly.

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

### -InstancePath

Represents the Device Instance path of a GPU in the host. This value can be obtained from the
"Name" property of the command `Get-VMHostPartitionableGpu`.

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

Specifies the virtual machine on which the network adapter is to be added.

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

### -VMName

Specifies the name of the virtual machine on which the network adapter is to be added.

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

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### System.String[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter

## NOTES

## RELATED LINKS

[Get-VMGpuPartitionAdapter](get-vmgpupartitionadapter.md)

[Remove-VMGpuPartitionAdapter](remove-vmgpupartitionadapter.md)

[Set-VMGpuPartitionAdapter](set-vmgpupartitionadapter.md)
