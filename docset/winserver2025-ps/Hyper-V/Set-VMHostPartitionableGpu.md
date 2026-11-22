---
description: Configures the host partitionable GPU to the number of partitions supported by the manufacturer.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmhostpartitionablegpu?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMHostPartitionableGpu
---

# Set-VMHostPartitionableGpu

## SYNOPSIS
Configures the host partitionable GPU to the number of partitions supported by the manufacturer.

## SYNTAX

### ComputerName (Default)

```
Set-VMHostPartitionableGpu [[-ComputerName] <String[]>] [[-Credential] <PSCredential[]>] [-Passthru]
 [-PartitionCount <UInt16>] [<CommonParameters>]
```

### CimSession

```
Set-VMHostPartitionableGpu [-CimSession] <CimSession[]> [-Passthru] [-PartitionCount <UInt16>]
 [<CommonParameters>]
```

### Object

```
Set-VMHostPartitionableGpu [-HostPartitionableGpu] <VMHostPartitionableGpu[]> [-Passthru]
 [-PartitionCount <UInt16>] [<CommonParameters>]
```

### Name

```
Set-VMHostPartitionableGpu [-Passthru] [-Name <String>] [-PartitionCount <UInt16>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-VMHostPartitionableGpu` cmdlet configures the host partitionable GPU to the number of
partitions supported by the manufacturer.

## EXAMPLES

### Example 1

```powershell
Set-VMHostPartitionableGpu -ComputerName "MyHost" -PartitionCount 8
```

This example partitions a GPU in a specific host into eight partitions.

### Example 2

```powershell
$GPU = Get-VMHostPartitionableGpu -Name "GPUDeviceIDName"
Set-VMHostPartitionableGpu -Name $GPU -PartitionCount 4
```

This example partitions a GPU in a host into four partitions by using the GPU device ID name.

## PARAMETERS

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Specifies one or more Hyper-V hosts on the virtual network adapters are to be retrieved. NetBIOS
names, IP addresses, and fully qualified domain names are allowed. The default is the local
computer. Use localhost or a dot (`.`) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies one or more user accounts that have permission to perform this action. The default is the
current user.

```yaml
Type: PSCredential[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPartitionableGpu

Full GPU object, obtained by executing `Get-VMHostPartitionableGpu`.

```yaml
Type: VMHostPartitionableGpu[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the GPU.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionCount

Specifies the number of partitions that the GPU will assign. The number of partitions is defined by
the manufacturer.

```yaml
Type: UInt16
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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### Microsoft.Management.Infrastructure.CimSession[]

### Microsoft.HyperV.PowerShell.VMHostPartitionableGpu[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostPartitionableGpu

## NOTES

## RELATED LINKS

[Get-VMHostPartitionableGpu](get-vmhostpartitionablegpu.md)
