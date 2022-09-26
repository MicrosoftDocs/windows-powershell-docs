---
description: Add GPU Partition adapter to a virtual machine
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 09/22/2022
online version: https://learn.microsoft.com/en-us/powershell/module/hyper-v/add-vmgpupartitionadapter?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMGpuPartitionAdapter

## SYNOPSIS
Add GPU Partition adapter to a virtual machine

## SYNTAX

### VMName (Default)
```
Add-VMGpuPartitionAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-Passthru] [-InstancePath <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMGpuPartitionAdapter [-VM] <VirtualMachine[]> [-Passthru] [-InstancePath <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMGpuPartitionAdapter** cmdlet adds GPU Partition adapter to a virtual machine. With no parameter, it assigns a Full partition from an assignable GPU to a VM.

## EXAMPLES

### Example 1
```powershell
PS C:\> $vm = Get-VM -name "TestVM"
Add-VMGpuPartitionAdapter -VM $vm
```

Assign a partition to a specific VM object. If you want to assign multiple GPU partitions run this command the number of times equal to the number of GPU partitions needed

### Example 2
```powershell
PS C:\> $vm = Get-VM -name "TestVM"
Add-VMGpuPartitionAdapter -VM $vm -Instancepath "SampleGPUInstancePath"
```

Assign a partition from a specific GPU to a VM. Where the instance path is the GPU device ID name on the Host

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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
Specifies one or more Hyper-V hosts from which virtual machines are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

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
Represents the Device Instance path of a GPU in the host. This value can be obtained from the  “Name” property of the command Get-VMHostPartitionableGpu

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
Maximum number of compute assigned by the Host GPU. This is defined by the manufacturer driver.

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
Maximum number of decoders assigned by the Host GPU. This is defined by the manufacturer driver.

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
Maximum number of encoders assigned by the Host GPU. This is defined by the manufacturer driver.

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
Maximum VRAM supported by the Host GPU. This is defined by the manufacturer driver.

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
Minimum number of compute assigned by the Host GPU. This is defined by the manufacturer driver.

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
Minimum number of decoders assigned by the Host GPU. This is defined by the manufacturer driver.

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
Minimum number of encoders assigned by the Host GPU. This is defined by the manufacturer driver.

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
Minimum VRAM supported by the Host GPU. This is defined by the manufacturer driver.

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
Optimal number of compute assigned by the Host GPU. This is defined by the manufacturer driver.

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
Optimal number of decoders assigned by the Host GPU. This is defined by the manufacturer driver.

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
Optimal number of encoders assigned by the Host GPU. This is defined by the manufacturer driver.

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
Optimal VRAM supported by the Host GPU. This is defined by the manufacturer driver.

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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### System.String[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter

## NOTES

## RELATED LINKS
