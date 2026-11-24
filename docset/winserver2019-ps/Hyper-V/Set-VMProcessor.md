---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmprocessor?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMProcessor
---

# Set-VMProcessor

## SYNOPSIS
Configures settings for the virtual processors of a virtual machine. Settings are applied uniformly to all virtual processors belonging to the virtual machine.

## SYNTAX

### VMName (Default)
```
Set-VMProcessor [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-Count <Int64>] [-CompatibilityForMigrationEnabled <Boolean>]
 [-CompatibilityForOlderOperatingSystemsEnabled <Boolean>] [-HwThreadCountPerCore <Int64>] [-Maximum <Int64>]
 [-Reserve <Int64>] [-RelativeWeight <Int32>] [-MaximumCountPerNumaNode <Int32>]
 [-MaximumCountPerNumaSocket <Int32>] [-ResourcePoolName <String>] [-Perfmon <String>] [-EnableHostResourceProtection <Boolean>]
 [-ExposeVirtualizationExtensions <Boolean>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMProcessor [-VM] <VirtualMachine[]> [-Count <Int64>] [-CompatibilityForMigrationEnabled <Boolean>]
 [-CompatibilityForOlderOperatingSystemsEnabled <Boolean>] [-HwThreadCountPerCore <Int64>] [-Maximum <Int64>]
 [-Reserve <Int64>] [-RelativeWeight <Int32>] [-MaximumCountPerNumaNode <Int32>]
 [-MaximumCountPerNumaSocket <Int32>] [-ResourcePoolName <String>] [-EnableHostResourceProtection <Boolean>]
 [-ExposeVirtualizationExtensions <Boolean>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMProcessor
```
Set-VMProcessor [-VMProcessor] <VMProcessor[]> [-Count <Int64>] [-CompatibilityForMigrationEnabled <Boolean>]
 [-CompatibilityForOlderOperatingSystemsEnabled <Boolean>] [-HwThreadCountPerCore <Int64>] [-Maximum <Int64>]
 [-Reserve <Int64>] [-RelativeWeight <Int32>] [-MaximumCountPerNumaNode <Int32>]
 [-MaximumCountPerNumaSocket <Int32>] [-ResourcePoolName <String>] [-EnableHostResourceProtection <Boolean>]
 [-ExposeVirtualizationExtensions <Boolean>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMProcessor** cmdlet configures the virtual processors of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMProcessor TestVM -Count 2 -Reserve 10 -Maximum 75 -RelativeWeight 200
```

Configures virtual machine TestVM with two virtual processors, a reserve of 10%, a limit of 75%, and a relative weight of 200.

### Example 2
```
PS C:\> Set-VMProcessor TestVM -CompatibilityForMigrationEnabled $true
```

Configures virtual machine TestVM, enabling processor compatibility for live migration.

### Example 3
```
PS C:\> Set-VMProcessor TestVM -CompatibilityForOlderOperatingSystemsEnabled $true
```

Configures virtual machine TestVM, enabling compatibility for running older operating systems.

### Example 4
```
PS C:\> Set-VMProcessor TestVM -ExposeVirtualizationExtensions $true
```

Configures virtual machine TestVM, enabling embedded Hyper-V.Uu

### Example 5
```
PS C:\> Set-VMProcessor TestVM -Perfmon pmu,pebs,lbr 
```

Configure your VM to expose PMU, PEBS, LBR for Performance Monitoring.





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

### -CompatibilityForMigrationEnabled
Specifies whether the virtual processor's features are to be limited for compatibility when migrating the virtual machine to another host.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompatibilityForOlderOperatingSystemsEnabled
Specifies whether the virtual processor's features are to be limited for compatibility with older operating systems.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which processors are to be configured.
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

### -Count
Specifies the number of virtual processors for the virtual machine.

```yaml
Type: Int64
Parameter Sets: (All)
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

### -EnableHostResourceProtection
Specifies whether to enable host resource protection on the virtual machine. When enabled, the host will enforce limits on some aspects of the virtual machine's activity, preventing excessive consumption of host compute resources. VM activities controlled by this setting include the VMbus pipe messages associated with a subset of the VM's virtual devices, and intercepts generated by the VM. The virtual devices affected include the video, keyboard, mouse, and dynamic memory VDEVs.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExposeVirtualizationExtensions
Specifies whether the hypervisor should expose the presence of virtualization extensions to the virtual machine, which enables support for nested virtualization.


```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HwThreadCountPerCore
Specifies the number of virtual SMT threads exposed to the virtual machine. Setting this value to 0 indicates the virtual machine will inherit the host's number of threads per core. This setting may not exceed the host's number of threads per core.

Note: Windows Server 2016 does not support setting HwThreadCountPerCore to 0. For more details, see [Configuring VM SMT settings using PowerShell](/windows-server/virtualization/hyper-v/manage/about-hyper-v-scheduler-type-selection#configuring-vm-smt-settings-using-powershell).

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximum
Specifies the maximum percentage of resources available to the virtual machine processor to be configured.
Allowed values range from 0 to 100.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumCountPerNumaNode
Specifies the maximum number of processors per NUMA node to be configured for the virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumCountPerNumaSocket
Specifies the maximum number of sockets per NUMA node to be configured for the virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Perfmon
Specifies the hardware to be Exposed for Performance Monitoring. For more information about requirements, visit [Enable Intel Performance Monitoring Hardware in a Hyper-V virtual machine](/windows-server/virtualization/hyper-v/manage/performance-monitoring-hardware).


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



### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.Processor** is to be passed through to the pipeline representing the processor to be configured.

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

### -RelativeWeight
Specifies the priority for allocating the physical computer's processing power to this virtual machine relative to others.
Allowed values range from 1 to 10000.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reserve
Specifies the percentage of processor resources to be reserved for this virtual machine.
Allowed values range from 0 to 100.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the processor resource pool to be used.

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

### -VM
Specifies the virtual machine on which the processor is to be configured.

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
Specifies the name of the virtual machine on which the processor is to be configured.

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

### -VMProcessor
Specifies that the virtual machine's settings for virtual processors are to be configured.

```yaml
Type: VMProcessor[]
Parameter Sets: VMProcessor
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMProcessor
If **-PassThru** is specified.

## NOTES

## RELATED LINKS
