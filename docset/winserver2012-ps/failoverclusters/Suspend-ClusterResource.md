---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/suspend-clusterresource?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Suspend-ClusterResource

## SYNOPSIS
Turns on maintenance for a disk resource or Cluster Shared Volume (CSV) so that you can run a disk maintenance tool without triggering failover.

## SYNTAX

```
Suspend-ClusterResource [[-Name] <String>] [-Cluster <String>] [-Force] [-InputObject <PSObject>]
 [-RedirectedAccess] [-VolumeName <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Suspend-ClusterResource** cmdlet turns on maintenance for a disk resource or Cluster Shared Volume (CSV) so that a disk maintenance tool can be run without triggering failover.

This cmdlet only applies to disks and CSVs.
For Cluster Shared Volumes, turning on maintenance takes dependent resources offline, which interrupts client access.
For other disks (LUNs) in cluster storage, turning on maintenance leaves dependent resources online.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Suspend-ClusterResource -Name "Cluster Disk 2"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 2      Online(Maintenance) Available Storage   Physical Disk
```

This example turns on maintenance for CSV named Cluster Disk 2 so that you can run a disk maintenance tool without triggering failover.

### EXAMPLE 2
```
PS C:\>Get-ClusterSharedVolume -Name "Cluster Disk 5" | Suspend-ClusterResource
Name                       State                      Node 
----                       -----                      ---- 
Cluster Disk 5             Online                     node2
```

This example turns on maintenance for all volumes on the CSV named Cluster Disk 5.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectedAccess
Causes CSV access to the storage device to be redirected over the network through another cluster node.
This parameter is only applicable to CSVs.

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

### -VolumeName
Specifies the name of the volume to suspend.
This parameter is only applicable to Cluster Shared Volumes (CSVs).
If this parameter is not specified, then the operation will be performed on all volumes on the CSV.

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

