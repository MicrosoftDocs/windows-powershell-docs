---
author: Kateyanne
description: 
external help file: StorSpaces2_Cmdlets.xml
manager: jasgro
Module Name: StorageSpaces
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storagespaces/get-spacesphysicaldisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SpacesPhysicalDisk
---

# Get-SpacesPhysicalDisk

## SYNOPSIS
Gets all PhysicalDisk objects that can be used with Storage Spaces to form a storage pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-SpacesPhysicalDisk [-OnlyListAvailable] [[-BusType] <String>] [[-Throttle] <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-SpacesPhysicalDisk [-OnlyListAvailable] [[-BusType] <String>] [-ClusterFriendlyName] <String>
 [[-Throttle] <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-SpacesPhysicalDisk [-OnlyListAvailable] [[-BusType] <String>] [-ServerToCompare] <String[]>
 [[-Throttle] <Int32>]
```

## DESCRIPTION
The Get-SpacesPhysicalDisk cmdlet gets all PhysicalDisk objects that are available to use with Storage Spaces.

## EXAMPLES

### Example 1 - Display physical disks
```
PS C:\>Get-SpacesPhysicalDisk
FriendlyName        CanPool             OperationalStatus   HealthStatus        Usage                              Size

------------        -------             -----------------   ------------        -----                              ----

PhysicalDisk1       False               OK                  Healthy             Auto-Select                   999.25 GB

PhysicalDisk2       False               OK                  Healthy             Auto-Select                   999.25 GB

PhysicalDisk3       False               OK                  Healthy             Auto-Select                   999.25 GB

PhysicalDisk4       True                OK                  Healthy             Auto-Select                     1000 GB

PhysicalDisk5       True                OK                  Healthy             Auto-Select                     1000 GB

PhysicalDisk6       True                OK                  Healthy             Auto-Select                     1000 GB

PhysicalDisk0       False               OK                  Healthy             Auto-Select                       40 GB
```

This example displays all physical disks available to Storage Spaces on the local computer.

### Example 2 - Display physical disks not in a pool
```
PS C:\>Get-SpacesPhysicalDisk -OnlyListAvailable
```

This example displays physical disks that are not currently allocated to a storage pool.

### Example 3 - Display physical disks common to the local computer and remote servers
```
PS C:\>Get-SpacesPhysicalDisk -ServerToCompare BigOrange1, BigOrange2
```

This example displays all common physical disks between the local computer and two servers, BigOrange1 and BigOrange2.

### Example 4 - Display physical disks common to a failover cluster
```
PS C:\>Get-SpacesPhysicalDisk -ClusterFriendlyName DeepSpaceCluster
```

This example displays all common physical disks among nodes in cluster named DeepSpaceCluster.

## PARAMETERS

### -BusType
Specifies on which bus to obtain PhysicalDisk objects.
The acceptable values for this parameter are: **iSCSI**, **SAS**, **SATA**, and **USB**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterFriendlyName
```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlyListAvailable
Specifies that the cmdlet should only get PhysicalDisk objects that are available to add to a storage pool (they do not already belong to a storage pool other than the primordial pool).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerToCompare
Gets all physical disks that are common between the local computer and the specified remote computers.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Throttle
```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
This cmdlet returns objects that represent physical disks.

## NOTES

## RELATED LINKS

