---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/suspend-clusterresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-ClusterResource
---

# Suspend-ClusterResource

## SYNOPSIS
Turns on maintenance for a disk resource or CSV so that you can run a disk maintenance tool without
triggering failover.

## SYNTAX

```
Suspend-ClusterResource [[-Name] <String>] [-VolumeName <String>] [-RedirectedAccess] [-Force]
 [-InputObject <PSObject>] [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Suspend-ClusterResource` cmdlet turns on maintenance for a disk resource or Cluster Shared
Volume (CSV) so that a disk maintenance tool can be run without triggering failover.

This cmdlet only applies to disks and CSVs. For Cluster Shared Volumes, turning on maintenance takes
dependent resources offline, which interrupts client access. For other disks, Logical Unit Number
(LUNs), in cluster storage, turning on maintenance leaves dependent resources online.

## EXAMPLES

### Example 1: Turn on maintenance for a CSV

```powershell
Suspend-ClusterResource -Name "Cluster Disk 2"
```

This example turns on maintenance for CSV named `Cluster Disk 2` so that you can run a disk
maintenance tool without triggering failover.

### Example 2: Turn on maintenance for multiple volumes

```powershell
Get-ClusterSharedVolume -Name "Cluster Disk 5" | Suspend-ClusterResource
```

This example turns on maintenance for all volumes on the CSV named `Cluster Disk 5`.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -Force

Forces the command to run without asking for user confirmation.

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

### -InputObject

Specifies the cluster resource, a disk or CSV, to suspend.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the cluster resource, a disk or CSV, to suspend.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectedAccess

Causes CSV access to the storage device to be redirected over the network through another cluster
node. This parameter is only applicable to CSVs.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: FileSystemRedirectedAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeName

Specifies the name of the volume to suspend. This parameter is only applicable to CSVs. If this
parameter isn't specified, then the operation will be performed on all volumes on the CSV.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterResource](./Add-ClusterResource.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Remove-ClusterResource](./Remove-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)
