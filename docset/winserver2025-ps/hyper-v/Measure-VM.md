---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/measure-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-VM
---

# Measure-VM

## SYNOPSIS
Reports resource utilization data for one or more virtual machines.

## SYNTAX

### Name (Default)
```
Measure-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [<CommonParameters>]
```

### VMObject
```
Measure-VM [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Measure-VM** cmdlet reports data on processor usage, memory usage, network traffic, and disk capacity for one or more virtual machines.

Note: Data is available for reporting through the **Measure-VM** cmdlet only after resource metering is enabled for a virtual machine.

The report has the following fields:

 -- ComputerName: The name of the virtual machine host.

 -- VMId: The unique identifier of the virtual machine.

 -- VMName: The friendly name of the virtual machine.

 -- HardDiskMetrics: Information about the performance and throughput of the storage subsystem.

 -- MeteringDuration: The duration over which resource utilization data is being reported.

 -- AverageProcessorUsage: The average processor usage, in megahertz, of the virtual machine over the period reported in the MeteringDuration field.

 -- AverageMemoryUsage: The average memory usage, in megabytes, of the virtual machine over the period reported in the MeteringDuration field.

 -- MaximumMemoryUsage: The maximum memory usage, in megabytes, of the virtual machine over the period reported in the MeteringDuration field.

 -- MinimumMemoryUsage: The minimum memory usage, in megabytes, of the virtual machine over the time period reported in the MeteringDuration field.

 -- TotalDiskAllocation: The maximum disk capacity, in megabytes, allocated to the virtual machine over the time period reported in the MeteringDuration field.
For more information, see the 'Notes' following the field descriptions.

 -- NetworkMeteredTrafficReport: An array whose elements report the traffic through each NetworkAdapterAcl on the virtual machine or machines over the time period reported in the MeteringDuration field.
Each array element has the following properties:

 -- NetworkAdapter: The virtual machine network adapter object on which the NetworkAdapterAcl has been configured.

 -- LocalAddress: for an inbound packet, the destination IP address in the packet header; for an outbound packet, the source IP address in the packet header.

 -- RemoteAddress: for an inbound packet, the source IP address in the packet header; for an outbound packet, the destination IP address in the packet header.

 -- Direction: the direction of the network traffic to which the ACL applies.
Allowed values are Inbound, Outbound, or Both.

 -- TotalTraffic: the amount of network traffic, in megabytes, through the NetworkAdapterAcl.

Notes:

 -- The disk capacity allocated to the virtual machine is reported as the sum of two totals -- the total storage capacity of all attached virtual hard disks, and the total amount of physical storage consumed by the virtual machine's snapshots.

 -- If the virtual machine has more than one virtual hard disk, then the TotalDiskAllocation property displays the sum of disk capacity allocated to all virtual hard disks.

 -- Resource utilization is not reported for disks attached through a virtual Fiber Channel connection or network adapters configured to use single-root I/O virtualization (SR-IOV).

 -- If the virtual machine is configured with static memory rather than Dynamic Memory, then AverageMemoryUsage, MinimumMemoryUsage, and MaximumMemoryUsage metrics equals the memory amount configured for the virtual machine.

The default display of a resource pool resource utilization report includes the following columns:

 -- VMName: The name of the virtual machine.

 -- AvgCPU(Mhz): The average processor usage, in megahertz, of the virtual machine.

 -- TotalDisk(M): The average disk usage, in megabytes, of the virtual machine.
For more information, see the 'Notes' following the field descriptions.

 -- NetworkInbound(M): Total incoming network traffic, in megabytes, to the virtual machine.

 -- NetworkOutbound(M): Total outgoing network traffic, in megabytes, from the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Measure-VM -VMName TestVM
```

This example reports resource utilization data for a virtual machine named TestVM.

### Example 2
```
PS C:\> $UtilizationReport = Get-VM TestVM | Measure-VM
PS C:\> Get-VM TestVM | Reset-VMResourceMetering
```

This example uses two commands as well as the pipeline.
The first command uses the **Get-VM** cmdlet and passes the object to the **Measure-VM** cmdlet to retrieve collected resource utilization data for a virtual machine named TestVM, and stores the data in a variable named $UtilizationReport.
The second command uses the **Reset-VMResourceMetering** cmdlet to clear existing data so that Hyper-V begins collecting new data.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more virtual machine hosts for which resource utilization is to be reported.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
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
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the virtual machine whose resource utilization data will be reported.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose resource utilization will be reported.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMMeteringReportForVirtualMachine

## NOTES

## RELATED LINKS

[Add-VMNetworkAdapterAcl](./Add-VMNetworkAdapterAcl.md)

[Disable-VMResourceMetering](./Disable-VMResourceMetering.md)

[Enable-VMResourceMetering](./Enable-VMResourceMetering.md)

[Remove-VMNetworkAdapterAcl](./Remove-VMNetworkAdapterAcl.md)

[Reset-VMResourceMetering](./Reset-VMResourceMetering.md)

