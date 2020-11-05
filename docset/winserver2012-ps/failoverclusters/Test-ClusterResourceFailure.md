---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 603DAB8D-743A-42B0-BAAE-9E32770C966B
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Test-ClusterResourceFailure

## SYNOPSIS
Simulates a failure of a cluster resource.

## SYNTAX

```
Test-ClusterResourceFailure [[-Name] <String>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Test-ClusterResourceFailure** cmdlet simulates a failure of a cluster resource.

Based on the failover and failback policies, when this cmdlet runs, the Cluster service moves the clustered role, or resource group, and attempts to bring the clustered resource online.
This cmdlet can be used to simulate what actions the Cluster service will take when a resource fails.

## EXAMPLES

### Example 1
```
PS C:\>Test-ClusterResourceFailure -Name "Cluster Disk 4"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 4      Failed              cluster12FS         Physical Disk
```

This example simulates a failure in cluster resource named Cluster Disk 4.

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
Specifies the cluster resource of which to simulate failure.

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
Specifies the name of the cluster resource of which to simulate failure.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Start-ClusterResource](./Start-ClusterResource.md)

