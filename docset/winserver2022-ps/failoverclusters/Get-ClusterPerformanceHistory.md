---
description: Get-ClusterPerformanceHistory
external help file: Microsoft.FailoverClusters.Health.PowerShell-help.xml
Module Name: FailoverClusters
ms.date: 08/31/2021
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clusterperformancehistory?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterPerformanceHistory
---

# Get-ClusterPerformanceHistory

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByCluster (Default)
```
Get-ClusterPerformanceHistory [[-ClusterSeriesName] <String[]>] [[-TimeFrame] <String>] [[-Cluster] <Cluster>]
 [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Api
```
Get-ClusterPerformanceHistory -SeriesKeyName <String> -Stream <String> [-CimSession <CimSession>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByClusterNode
```
Get-ClusterPerformanceHistory [[-ClusterNodeSeriesName] <String[]>] [[-TimeFrame] <String>]
 [-ClusterNode] <ClusterNode[]> [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVM
```
Get-ClusterPerformanceHistory [[-VMSeriesName] <String[]>] [[-TimeFrame] <String>] [-VM] <PSObject[]>
 [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVHD
```
Get-ClusterPerformanceHistory [[-VHDSeriesName] <String[]>] [[-TimeFrame] <String>] [-VHD] <PSObject[]>
 [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-ClusterPerformanceHistory [[-PhysicalDiskSeriesName] <String[]>] [[-TimeFrame] <String>]
 [-PhysicalDisk] <CimInstance[]> [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVolume
```
Get-ClusterPerformanceHistory [[-VolumeSeriesName] <String[]>] [[-TimeFrame] <String>]
 [-Volume] <CimInstance[]> [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNetAdapter
```
Get-ClusterPerformanceHistory [[-NetAdapterSeriesName] <String[]>] [[-TimeFrame] <String>]
 [-NetworkAdapter] <CimInstance[]> [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
{{ Fill Cluster Description }}

```yaml
Type: Cluster
Parameter Sets: ByCluster
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClusterNode
{{ Fill ClusterNode Description }}

```yaml
Type: ClusterNode[]
Parameter Sets: ByClusterNode
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClusterNodeSeriesName
{{ Fill ClusterNodeSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByClusterNode
Aliases:
Accepted values: ClusterNode.Cpu.Usage, ClusterNode.Cpu.Usage.Guest, ClusterNode.Memory.Usage.Guest, VM.Memory.Maximum, ClusterNode.Memory.Usage.Host, ClusterNode.Cpu.Usage.Host, ClusterNode.Memory.Total, ClusterNode.Memory.Available, ClusterNode.Memory.Usage, NetAdapter.Bandwidth.Inbound, NetAdapter.Bandwidth.Outbound, NetAdapter.Bandwidth.Total, NetAdapter.Bandwidth.RDMA.Inbound, NetAdapter.Bandwidth.RDMA.Outbound, NetAdapter.Bandwidth.RDMA.Total, PhysicalDisk.Capacity.Size.Used, PhysicalDisk.Capacity.Size.Total, PhysicalDisk.Cache.Size.Total, PhysicalDisk.Cache.Size.Dirty, ClusterNode.CsvCache.Iops.Read.Hit, ClusterNode.CsvCache.Iops.Read.Miss, ClusterNode.CsvCache.Iops.Read.HitRate, ClusterNode.SblCache.Iops.Read.Hit, ClusterNode.SblCache.Iops.Read.Miss, ClusterNode.SblCache.Iops.Read.HitRate, ClusterNode.Storage.Degraded

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterSeriesName
{{ Fill ClusterSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByCluster
Aliases:
Accepted values: Volume.IOPS.Read, Volume.IOPS.Write, Volume.IOPS.Total, Volume.Throughput.Read, Volume.Throughput.Write, Volume.Throughput.Total, Volume.Latency.Read, Volume.Latency.Write, Volume.Latency.Average, ClusterNode.Cpu.Usage, ClusterNode.Cpu.Usage.Guest, ClusterNode.Memory.Usage.Guest, VM.Memory.Maximum, ClusterNode.Memory.Available, ClusterNode.Memory.Total, ClusterNode.Memory.Usage.Host, ClusterNode.Memory.Usage, ClusterNode.Cpu.Usage.Host, Volume.Size.Available, Volume.Size.Total, PhysicalDisk.Capacity.Size.Used, PhysicalDisk.Capacity.Size.Total, PhysicalDisk.Cache.Size.Total, PhysicalDisk.Cache.Size.Dirty, ClusterNode.CsvCache.Iops.Read.Hit, ClusterNode.CsvCache.Iops.Read.Miss, ClusterNode.CsvCache.Iops.Read.HitRate, ClusterNode.SblCache.Iops.Read.Hit, ClusterNode.SblCache.Iops.Read.Miss, ClusterNode.SblCache.Iops.Read.HitRate

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetAdapterSeriesName
{{ Fill NetAdapterSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByNetAdapter
Aliases:
Accepted values: NetAdapter.Bandwidth.Inbound, NetAdapter.Bandwidth.Outbound, NetAdapter.Bandwidth.Total, NetAdapter.Bandwidth.RDMA.Inbound, NetAdapter.Bandwidth.RDMA.Outbound, NetAdapter.Bandwidth.RDMA.Total

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkAdapter
{{ Fill NetworkAdapter Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByNetAdapter
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDisk
{{ Fill PhysicalDisk Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByPhysicalDisk
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDiskSeriesName
{{ Fill PhysicalDiskSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByPhysicalDisk
Aliases:
Accepted values: PhysicalDisk.IOPS.Read, PhysicalDisk.IOPS.Write, PhysicalDisk.IOPS.Total, PhysicalDisk.Throughput.Read, PhysicalDisk.Throughput.Write, PhysicalDisk.Throughput.Total, PhysicalDisk.Latency.Read, PhysicalDisk.Latency.Write, PhysicalDisk.Latency.Average, PhysicalDisk.Capacity.Size.Used, PhysicalDisk.Capacity.Size.Total, PhysicalDisk.Cache.Size.Total, PhysicalDisk.Cache.Size.Dirty

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SeriesKeyName
{{ Fill SeriesKeyName Description }}

```yaml
Type: String
Parameter Sets: Api
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stream
{{ Fill Stream Description }}

```yaml
Type: String
Parameter Sets: Api
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeFrame
{{ Fill TimeFrame Description }}

```yaml
Type: String
Parameter Sets: ByCluster, ByClusterNode, ByVM, ByVHD, ByPhysicalDisk, ByVolume, ByNetAdapter
Aliases:
Accepted values: MostRecent, LastHour, LastDay, LastWeek, LastMonth, LastYear

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHD
{{ Fill VHD Description }}

```yaml
Type: PSObject[]
Parameter Sets: ByVHD
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VHDSeriesName
{{ Fill VHDSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByVHD
Aliases:
Accepted values: VHD.Latency.Average, VHD.Throughput.Read, VHD.Throughput.Write, VHD.Throughput.Total, VHD.IOPS.Read, VHD.IOPS.Write, VHD.IOPS.Total, VHD.Size.Current, VHD.Size.Maximum

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
{{ Fill VM Description }}

```yaml
Type: PSObject[]
Parameter Sets: ByVM
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSeriesName
{{ Fill VMSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByVM
Aliases:
Accepted values: VM.Cpu.Usage, VM.Memory.Total, VM.Memory.Available, VM.Memory.Pressure, VM.Memory.Assigned, VM.Memory.Minimum, VM.Memory.Maximum, VM.Memory.Startup, VHD.Latency.Average, VHD.Throughput.Read, VHD.Throughput.Write, VHD.Throughput.Total, VHD.IOPS.Read, VHD.IOPS.Write, VHD.IOPS.Total, VMNetworkAdapter.Bandwidth.Inbound, VMNetworkAdapter.Bandwidth.Outbound, VMNetworkAdapter.Bandwidth.Total

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
{{ Fill Volume Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByVolume
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeSeriesName
{{ Fill VolumeSeriesName Description }}

```yaml
Type: String[]
Parameter Sets: ByVolume
Aliases:
Accepted values: Volume.IOPS.Read, Volume.IOPS.Write, Volume.IOPS.Total, Volume.Throughput.Read, Volume.Throughput.Write, Volume.Throughput.Total, Volume.Latency.Read, Volume.Latency.Write, Volume.Latency.Average, Volume.Size.Available, Volume.Size.Total

Required: False
Position: 0
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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterNode[]

### System.Management.Automation.PSObject[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
