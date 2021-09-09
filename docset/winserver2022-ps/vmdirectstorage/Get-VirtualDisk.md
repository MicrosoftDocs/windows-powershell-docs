---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-VirtualDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByFriendlyName (Default)
```
Get-VirtualDisk [[-FriendlyName] <String[]>] [-Usage <Usage[]>] [-OtherUsageDescription <String[]>]
 [-IsSnapshot <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-VirtualDisk [-UniqueId <String[]>] [-Usage <Usage[]>] [-OtherUsageDescription <String[]>]
 [-IsSnapshot <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Get-VirtualDisk [-Name <String[]>] [-Usage <Usage[]>] [-OtherUsageDescription <String[]>]
 [-IsSnapshot <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageJob
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageJob <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTargetVirtualDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-TargetVirtualDisk <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BySourceVirtualDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-SourceVirtualDisk <CimInstance>] [-AssociatedObjects]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTargetPort
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-TargetPort <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInitiatorId
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-InitiatorId <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByMaskingSet
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-MaskingSet <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInitiatorPort
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-InitiatorPort <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-Disk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByStorageTier
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageTier <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageRack
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageRack <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageChassis
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageChassis <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageScaleUnit
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageScaleUnit <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageEnclosure
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageEnclosure <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-PhysicalDisk <CimInstance>] [-PhysicalRangeMin <UInt64>]
 [-PhysicalRangeMax <UInt64>] [-NoRedundancy] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePool
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StoragePool <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageNode
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageNode <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
{{ Fill AsJob Description }}

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

### -AssociatedObjects
{{ Fill AssociatedObjects Description }}

```yaml
Type: SwitchParameter
Parameter Sets: BySourceVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
{{ Fill CimSession Description }}

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

### -Disk
{{ Fill Disk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FriendlyName
{{ Fill FriendlyName Description }}

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
{{ Fill HealthStatus Description }}

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

### -InitiatorId
{{ Fill InitiatorId Description }}

```yaml
Type: CimInstance
Parameter Sets: ByInitiatorId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InitiatorPort
{{ Fill InitiatorPort Description }}

```yaml
Type: CimInstance
Parameter Sets: ByInitiatorPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsSnapshot
{{ Fill IsSnapshot Description }}

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

### -MaskingSet
{{ Fill MaskingSet Description }}

```yaml
Type: CimInstance
Parameter Sets: ByMaskingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

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

### -NoRedundancy
{{ Fill NoRedundancy Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
{{ Fill OtherUsageDescription Description }}

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

### -PhysicalDisk
{{ Fill PhysicalDisk Description }}

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

### -PhysicalRangeMax
{{ Fill PhysicalRangeMax Description }}

```yaml
Type: UInt64
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalRangeMin
{{ Fill PhysicalRangeMin Description }}

```yaml
Type: UInt64
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVirtualDisk
{{ Fill SourceVirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: BySourceVirtualDisk
Aliases: VirtualDisk

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageChassis
{{ Fill StorageChassis Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageChassis
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageEnclosure
{{ Fill StorageEnclosure Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageEnclosure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageJob
{{ Fill StorageJob Description }}

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
{{ Fill StorageNode Description }}

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

### -StoragePool
{{ Fill StoragePool Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageRack
{{ Fill StorageRack Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageRack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageScaleUnit
{{ Fill StorageScaleUnit Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageScaleUnit
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
{{ Fill StorageSubSystem Description }}

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
{{ Fill StorageTier Description }}

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

### -TargetPort
{{ Fill TargetPort Description }}

```yaml
Type: CimInstance
Parameter Sets: ByTargetPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetVirtualDisk
{{ Fill TargetVirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByTargetVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

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
{{ Fill UniqueId Description }}

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
{{ Fill Usage Description }}

```yaml
Type: Usage[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Other, Unrestricted, ReservedForComputerSystem, ReservedForReplicationServices, ReservedForMigrationServices, LocalReplicaSource, RemoteReplicaSource, LocalReplicaTarget, RemoteReplicaTarget, LocalReplicaSourceOrTarget, RemoteReplicaSourceOrTarget, DeltaReplicaTarget, ElementComponent, ReservedAsPoolContributer, CompositeVolumeMember, CompositeVirtualDiskMember, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk

## NOTES

## RELATED LINKS
