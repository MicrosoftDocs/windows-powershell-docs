---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StoragePool.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagepool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StoragePool
---

# Get-StoragePool

## SYNOPSIS
Gets a specific storage pool, or a set of StoragePool objects either from all storage subsystems across all storage providers, or optionally a filtered subset based on specific parameters.

## SYNTAX

### ByFriendlyName (Default)
```
Get-StoragePool [[-FriendlyName] <String[]>] [-Usage <Usage[]>] [-IsPrimordial <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByUniqueId
```
Get-StoragePool [-UniqueId <String[]>] [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Get-StoragePool [-Name <String[]>] [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUsage
```
Get-StoragePool [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsPrimordial <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageJob
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageJob <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVolume
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-Volume <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageTier
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageTier <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByResiliencySetting
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-ResiliencySetting <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-VirtualDisk <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-PhysicalDisk <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageNode
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageNode <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-StoragePool [-IsPrimordial <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageSubSystem <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StoragePool** cmdlet returns either a specific storage pool, or a set of StoragePool objects either from all storage subsystems across all storage providers, or optionally a filtered subset based on specific parameters.

## EXAMPLES

### Example 1: Get all storage pools
```
PS C:\>Get-StoragePool
FriendlyName            OperationalStatus       HealthStatus            IsPrimordial            IsReadOnly
------------            -----------------       ------------            ------------            ----------
CompanyData             OK                      Healthy                 False                   False
Primordial              OK                      Healthy                 True                    False
```

This example lists all storage pools, (when run without parameter) from all Storage Management Providers, from all storage subsystems.
This list may optionally be filtered using one or more parameters.

### Example 2: Get all storage pools (not including primordial pools)
```
PS C:\>Get-StoragePool -IsPrimordial $False
FriendlyName            OperationalStatus       HealthStatus            IsPrimordial            IsReadOnly
------------            -----------------       ------------            ------------            ----------
CompanyData             OK                      Healthy                 False                   False
```

This example lists all (concrete) storage pools, excluding primordial pools (which store physical disks that have yet to be added to a concrete storage pool).

### Example 3: Get all storage pools that support the Mirror resiliency setting
```
PS C:\>Get-ResiliencySetting -Name Mirror | Get-StoragePool
FriendlyName                  OperationalStatus             HealthStatus                  IsPrimordial                  IsReadOnly
------------                  -----------------             ------------                  ------------                  ----------
CompanyData                   OK                            Healthy                       False                         False
Primordial                    OK                            Healthy                       True                          False
```

This example uses the Get-ResiliencySetting cmdlet to retrieve ResiliencySetting objects that represent each storage pool that supports the specified resiliency setting (also known as storage layout), in this case Mirror, and then pipes the array of objects to the Get-StoragePool cmdlet.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the storage pool to get.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthStatus
Specifies the health status(es) of the storage pool to get.
Specify one or more of the following values: **Healthy**, **Warning**, Unhealthy, or Unknown.

```yaml
Type: HealthStatus[]
Parameter Sets: (All)
Aliases:
Accepted values: Healthy, Warning, Unhealthy, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPrimordial
Specifies whether to get (concrete) storage pools or primordial storage pools (which store physical disks that have yet to be added to a concrete storage pool).
To get (concrete) storage pools, specify the $False Boolean value.
To get primordial pools, specify the $True Boolean value.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage pool to get.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherUsageDescription
Gets any storage pools that match the specified OtherUsageDescription string.

```yaml
Type: String[]
Parameter Sets: ByUsage
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalDisk
Gets the storage pool that contains the specified PhysicalDisk object.
Enter a PhysicalDisk CIM object.
The Physical Disk CIM object is exposed by the Get-PhysicalDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResiliencySetting
Gets the storage pool associated with the specified ResiliencySetting object.
Enter a single ResiliencySetting CIM object as input, or pipe multiple ResiliencySetting objects to the Get-StoragePool cmdlet to view all pools that support the specified resiliency setting.
Resiliency Setting CIM objects are exposed by the Get-ResiliencySetting cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByResiliencySetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageJob
Specifies an outstanding storage job as a **CimInstance** object.
The cmdlet gets the storage pools associated with the storage job that you specify.
To obtain a storage job, use the Get-StorageJob cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageJob
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode
Specifies a storage node as a **CimInstance** object.
The cmdlet gets storage pools that have read-write access on the node that you specify.
To obtain a storage node object, use the Get-StorageNode cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Accepts a StorageSubsystem object as input.
The Storage Subsystem CIM object is exposed by the [Get-StorageSubsystem](https://technet.microsoft.com/library/ea364a0b-06d6-4653-b41c-be69b8038b54) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageTier
Specifies a storage tier as a **CimInstance** object.
The cmdlet gets storage pools that contain the storage tier that you specify.
To obtain a storage tier object, use the Get-StorageTier cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageTier
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -UniqueId
Specifies the UniqueID of the storage pool to get.
If the UniqueID includes brackets, enclose the string in quotation marks.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Gets any storage pools that match the specified Usage value.
Acceptable values: ReservedAsDeltaReplicaContainer, ReservedForComputerSystem, ReservedForLocalReplicationServices, ReservedForMigrationServices, ReservedForRemoteReplicationServices, ReservedForSparing, Unknown, Unrestricted, and Other

```yaml
Type: Usage[]
Parameter Sets: ByFriendlyName, ByUsage
Aliases:
Accepted values: Unknown, Other, Unrestricted, ReservedForComputerSystem, ReservedAsDeltaReplicaContainer, ReservedForMigrationServices, ReservedForLocalReplicationServices, ReservedForRemoteReplicationServices, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Gets the storage pool associated with the specified virtual disk object.
Enter a VirtualDisk CIM object.
The Virtual Disk CIM object is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Volume
Specifies a volume.
The cmdlet gets the storage nodes that correspond to the volume that you specify.
To obtain a **Volume** object, use the Get-Volume cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVolume
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can use the pipeline operator to pass an MSFT_PhysicalDisk object to the *PhysicalDisk* parameter to get the storage pool associated with the PhysicalDisk object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_ResiliencySetting
You can use the pipeline operator to pass an MSFT_ResiliencySetting object to the *ResiliencySetting* parameter to get the storage pool associated with the ResiliencySetting object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageNode
You can use the pipeline operator to pass an MSFT_StorageNode object to the *StorageNode* parameter to get the storage pool associated with the StorageNode object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an MSFT_StorageSubsystem object to the *StorageSubsystem* parameter to get the storage pool associated with the StorageSubsystem object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
You can use the pipeline operator to pass an MSFT_StorageTier object to the *StorageTier* parameter to get the storage pool associated with the StorageTier object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an MSFT_VirtualDisk object to the *VirtualDisk* parameter to get the storage pool associated with the VirtualDisk object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
The **Get-StoragePool** cmdlet returns objects representing storage pools.

## NOTES
* To reduce load times, storage providers other than the Storage Spaces provider might not perform a full discovery of objects on initial load. As a result, this cmdlet might show an empty or incomplete listing of objects from a particular storage provider. To update the storage provider cache so that storage objects are available from a storage provider, use the **Update-StorageProviderCache** cmdlet.
* The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Volume](./Get-Volume.md)

[New-StoragePool](./New-StoragePool.md)

[Remove-StoragePool](./Remove-StoragePool.md)

[Set-StoragePool](./Set-StoragePool.md)

[Get-StorageJob](./Get-StorageJob.md)

[Get-StorageNode](./Get-StorageNode.md)

[Get-StorageTier](./Get-StorageTier.md)

