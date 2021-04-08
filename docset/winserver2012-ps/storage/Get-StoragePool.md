---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-storagepool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-StoragePool

## SYNOPSIS
Gets a specific storage pool, or a set of StoragePool objects either from all storage subsystems across all storage providers, or optionally a filtered subset based on specific parameters.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-StoragePool [[-FriendlyName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-HealthStatus <HealthStatus[]>] [-IsPrimordial <Boolean[]>] [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-Name <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-PhysicalDisk <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-OtherUsageDescription <String[]>] [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ResiliencySetting <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_8
```
Get-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-StorageSubSystem <CimInstance>] [-ThrottleLimit <Int32>]
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
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Accepts a StorageSubsystem object as input.
The Storage Subsystem CIM object is exposed by the Get-StorageSubsystemhttp://technet.microsoft.com/library/ea364a0b-06d6-4653-b41c-be69b8038b54 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_8
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe an MSFT_PhysicalDisk object to the PhysicalDisk parameter to get the storage pool associated with the PhysicalDisk object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe an MSFT_StorageSubsystem object to the StorageSubsystem parameter to get the storage pool associated with the StorageSubsystem object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the VirtualDisk parameter to get the storage pool associated with the VirtualDisk object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
The **Get-StoragePool** cmdlet returns objects representing storage pools.

## NOTES
* To reduce load times, storage providers other than the Storage Spaces provider might not perform a full discovery of objects on initial load. As a result, this cmdlet might show an empty or incomplete listing of objects from a particular storage provider. To update the storage provider cache so that storage objects are available from a storage provider, use the **Update-StorageProviderCache** cmdlet.
* The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## RELATED LINKS

[New-StoragePool](./New-StoragePool.md)

[Remove-StoragePool](./Remove-StoragePool.md)

[Set-StoragePool](./Set-StoragePool.md)

