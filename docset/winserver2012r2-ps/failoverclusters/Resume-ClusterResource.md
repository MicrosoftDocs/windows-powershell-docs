---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Resume-ClusterResource
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: ACF82BAB-08BA-4D3B-AD60-A554F5AE0A7D
---

# Resume-ClusterResource

## SYNOPSIS
Turns off maintenance for a disk resource or Cluster Shared Volume within a failover cluster.

## SYNTAX

```
Resume-ClusterResource [[-Name] <String>] [-VolumeName <String>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Resume-ClusterResource** cmdlet turns off maintenance for a disk resource or Cluster Shared Volume within a failover cluster.

This cmdlet applies to disks and Cluster Shared Volumes only.
We recommend that maintenance be turned off for a disk or Cluster Shared Volume as soon as the maintenance tasks have been completed.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Resume-ClusterResource "Cluster Disk 2"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 2      Online              Available Storage   Physical Disk
```

This example turns off maintenance for the CSV named Cluster Disk 2.

### EXAMPLE 2
```
PS C:\>Get-ClusterSharedVolume "Cluster Disk 5" | Resume-ClusterResource
Name                       State                      Node 
----                       -----                      ---- 
Cluster Disk 5             Online                     node2
```

This example turns off maintenance for all volumes on the CSV named Cluster Disk 5.

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

### -InputObject
Specifies the cluster resource to resume.

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
Specifies the name of the cluster resource to resume.

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

### -VolumeName
Specifies the name of the volume to suspend.
This parameter is only applicable to Cluster Shared Volumes.
If this parameter is not specified, then the operation will be performed on all volumes on the Cluster Shared Volume.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)

