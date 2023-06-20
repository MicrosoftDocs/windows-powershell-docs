---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/measure-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Measure-VM

## SYNOPSIS
Reports resource utilization data for one or more virtual machines.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Measure-VM [-Name] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Measure-VM [-VM] <VirtualMachine[]>
```

## DESCRIPTION
The **Measure-VM** cmdlet reports data on processor usage, memory usage, network traffic, and disk capacity for one or more virtual machines.

Note: Data is available for reporting through the **Measure-VM** cmdlet only after resource metering is enabled for a virtual machine.

The report has the following fields:

 -- ComputerName: The name of the virtual machine host.

 -- VMId: The unique identifier of the virtual machine.

 -- VMName: The friendly name of the virtual machine.

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

 -- NetworkOutbound(M): Total outgoing network traffic, in megabytes, from the vritual machine.

## EXAMPLES

### Example 1
```
PS C:\>Measure-VM -VMName TestVM
```

This example reports resource utilization data for a virtual machine named TestVM.

### Example 2
```
PS C:\>$UtilizationReport = Get-VM TestVM | Measure-VM
PS C:\>Get-VM TestVM | Reset-VMResourceMetering
```

This example uses two commands as well as the pipeline.
The first command uses the Get-VM cmdlet and passes the object to the Measure-VM cmdlet to retrieve collected resource utilization data for a virtual machine named TestVM, and stores the data in a variable named $UtilizationReport.
The second command uses the Reset-VMResourceMetering cmdlet to clear existing data so that Hyper-V begins collecting new data.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts for which resource utilization is to be reported.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose resource utilization will be reported.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-VMNetworkAdapterAcl](./Add-VMNetworkAdapterAcl.md)

[Disable-VMResourceMetering](./Disable-VMResourceMetering.md)

[Enable-VMResourceMetering](./Enable-VMResourceMetering.md)

[Remove-VMNetworkAdapterAcl](./Remove-VMNetworkAdapterAcl.md)

[Reset-VMResourceMetering](./Reset-VMResourceMetering.md)

