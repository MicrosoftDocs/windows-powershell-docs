---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/measure-vmresourcepool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-VMResourcePool
---

# Measure-VMResourcePool

## SYNOPSIS
Reports resource utilization data for one or more resource pools.

## SYNTAX

```
Measure-VMResourcePool [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [[-ResourcePoolType] <VMResourcePoolType[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Measure-VMResourcePool** cmdlet reports data on processor usage, memory usage, network traffic, and disk capacity for one or more virtual machine resource pools.

Note: Data is available for reporting by the **Measure-VMResourcePool** cmdlet only after resource metering is enabled for the virtual machine resource pool or pools.

This cmdlet can also be called with an array of resource pools with the same name.
In this case, resource utilization data for different resource types will be aggregated in a single report.

The report has the following fields:

    -- ComputerName: The name of the virtual machine host.

    -- ResourcePoolType: The type of the virtual machine resource pool.

    -- ResourcePoolName: The name of the resource pool.

    -- MeteringDuration: The duration over which resource utilization data is being reported.

    -- AverageProcessorUsage: The sum of the average processor usage, in megahertz, of the virtual machines under the specified resource pool over the time period reported in the MeteringDuration field.

    -- AverageMemoryUsage: The sum of the average memory usage, in megabytes, of the virtual machines under the specified resource pool over the time period reported in the MeteringDuration field.

    -- MaximumMemoryUsage: The maximum memory usage, in megabytes, of any virtual machine under the specified resource pool over the time period reported in the MeteringDuration field.

    -- MinimumMemoryUsage: The minimum memory usage, in megabytes, of any virtual machine under the specified resource pool over the time period reported in the MeteringDuration field.

    -- TotalDiskAllocation: The maximum disk capacity, in gigabytes, allocated to any virtual machine under the specified resource pool over the time period reported in the MeteringDuration field.

    -- NetworkMeteredTrafficReport: An array whose elements report the traffic through each NetworkAdapterAcl on the virtual machines under the specified resource pool over the time period reported in the MeteringDuration field.

Each array element has the following properties:

    -- LocalAddress: for an inbound packet, the destination IP address in the packet header; for an outbound packet, the source IP address in the packet header.

    -- RemoteAddress: for an inbound packet, the source IP address in the packet header; for an outbound packet, the destination IP address in the packet header.

    -- Direction: the direction of the network traffic to which the ACL applies.
Allowed values are Inbound, Outbound, or Both.

    -- TotalTraffic: the amount of network traffic, in megabytes, through the NetworkAdapterAcl.

Notes:

    -- The disk capacity allocated to the virtual machine is reported as the sum of the virtual capacity of the virtual machine's virtual hard disks, together with the sum of the physical disk capacity of the virtual machine's virtual hard disk snapshots.

    -- Resource utilization information is not available for resource pool types of FiberChannelConnection, FibreChannelPort, VFD, and ISO.

    -- If the virtual machines under the specified resource pool are configured with the same values for LocalAddress, RemoteAddress, and Direction, the information from each of these NetworkAdapterAcl objects is aggregated in the TotalTraffic property specified by the NetworkMeteredTrafficReport of the object returned by the **Measure-VMResourcePool** cmdlet.

Default display of a resource pool resource utilization report includes the following columns:

    -- Name: the name of the resource pool.

    -- ResourcePoolType: the type of the virtual machine resource pool.

    --AvgCPU(Mhz): the sum of the average processor usage, in megahertz, of the virtual machines under the specified resource pool.

    -- AvgRAM(M): the sum of the average memory usage, in megabytes, of the virtual machines under the specified resource pool.

    -- TotalDisk(G): the maximum disk capacity, in gigabytes, allocated to any virtual machine under the specified resource pool.

    -- NetworkInbound(M): total incoming traffic, in megabytes, to the virtual machines under the specified resource pool.

    -- NetworkOutbound(M): total outgoing network traffic, in megabytes, to the virtual machines under the specified resource pool.

## EXAMPLES

### Example 1
```
PS C:\> Measure-VMResourcePool -Name TestResourcePool -ResourcePoolType Memory
```

This example reports resource utilization data for a resource pool named TestResourcePool.

### Example 2
```
PS C:\> $UtilizationReport = Get-VMResourcePool -Name "TestResourcePool" -ResourcePoolType @("Processor","VHD","Ethernet","Memory") | Measure-VMResourcePool
PS C:\> Get-VMResourcePool -ResourcePoolType @("Processor","VHD","Ethernet","Memory") | Reset-VMResourceMetering
```

This example uses two commands as well as the pipeline.
The first command retrieves resource utilization data for a set of resource pools using the **Get-VMResourcePool** cmdlet, passes the object to the **Measure-VMResourcePool** cmdlet, and stores that data in a variable named $UtilizationReport.
The second command resets resource utilization data for these resource pools so that Hyper-V begins collecting new data for the resource pools.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more virtual machine hosts for which resource utilization is to be reported.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the resource pool for which resource utilization is to be reported.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the resource type of the virtual machine resource pool for which resource utilization is to be reported.
Valid values are:

- Ethernet
- Memory
- Processor
- VHD

```yaml
Type: VMResourcePoolType[]
Parameter Sets: (All)
Aliases:
Accepted values: Ethernet, Memory, Processor, VHD

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VMResourcePoolType[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMMeteringReportForResourcePool

## NOTES

## RELATED LINKS

[Add-VMNetworkAdapterAcl](./Add-VMNetworkAdapterAcl.md)

[Disable-VMResourceMetering](./Disable-VMResourceMetering.md)

[Enable-VMResourceMetering](./Enable-VMResourceMetering.md)

[Remove-VMNetworkAdapterAcl](./Remove-VMNetworkAdapterAcl.md)

[Reset-VMResourceMetering](./Reset-VMResourceMetering.md)

