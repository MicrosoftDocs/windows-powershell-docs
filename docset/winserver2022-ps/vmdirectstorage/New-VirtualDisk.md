---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# New-VirtualDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByFriendlyName (Default)
```
New-VirtualDisk [-StoragePoolFriendlyName] <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>]
 [-IsEnclosureAware <Boolean>] [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-PhysicalDisksToUse <CimInstance[]>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-NumberOfGroups <UInt16>] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-ReadCacheSize <UInt64>]
 [-IsManualAttach <Boolean>] [-AddToCluster <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-VirtualDisk -StoragePoolUniqueId <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>]
 [-IsEnclosureAware <Boolean>] [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-PhysicalDisksToUse <CimInstance[]>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-NumberOfGroups <UInt16>] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-ReadCacheSize <UInt64>]
 [-IsManualAttach <Boolean>] [-AddToCluster <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByName
```
New-VirtualDisk -StoragePoolName <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>]
 [-IsEnclosureAware <Boolean>] [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-PhysicalDisksToUse <CimInstance[]>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-NumberOfGroups <UInt16>] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-ReadCacheSize <UInt64>]
 [-IsManualAttach <Boolean>] [-AddToCluster <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-VirtualDisk -InputObject <CimInstance[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>]
 [-IsEnclosureAware <Boolean>] [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-PhysicalDisksToUse <CimInstance[]>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-NumberOfGroups <UInt16>] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-ReadCacheSize <UInt64>]
 [-IsManualAttach <Boolean>] [-AddToCluster <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
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

### -AddToCluster
{{ Fill AddToCluster Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllocationUnitSize
{{ Fill AllocationUnitSize Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AutoNumberOfColumns
{{ Fill AutoNumberOfColumns Description }}

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

### -AutoWriteCacheSize
{{ Fill AutoWriteCacheSize Description }}

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

### -ColumnIsolation
{{ Fill ColumnIsolation Description }}

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaultDomainAwareness
{{ Fill FaultDomainAwareness Description }}

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskFriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Interleave
{{ Fill Interleave Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsEnclosureAware
{{ Fill IsEnclosureAware Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsManualAttach
{{ Fill IsManualAttach Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaType
{{ Fill MediaType Description }}

```yaml
Type: MediaType
Parameter Sets: (All)
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumns
{{ Fill NumberOfColumns Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfDataCopies
{{ Fill NumberOfDataCopies Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfGroups
{{ Fill NumberOfGroups Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
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
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDiskRedundancy
{{ Fill PhysicalDiskRedundancy Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: FaultDomainRedundancy

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisksToUse
{{ Fill PhysicalDisksToUse Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningType
{{ Fill ProvisioningType Description }}

```yaml
Type: ProvisioningType
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Thin, Fixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadCacheSize
{{ Fill ReadCacheSize Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingName
{{ Fill ResiliencySettingName Description }}

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

### -Size
{{ Fill Size Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFaultDomainsToUse
{{ Fill StorageFaultDomainsToUse Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
{{ Fill StoragePoolFriendlyName Description }}

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoragePoolName
{{ Fill StoragePoolName Description }}

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoragePoolUniqueId
{{ Fill StoragePoolUniqueId Description }}

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StoragePoolId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageTiers
{{ Fill StorageTiers Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierSizes
{{ Fill StorageTierSizes Description }}

```yaml
Type: UInt64[]
Parameter Sets: (All)
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

### -Usage
{{ Fill Usage Description }}

```yaml
Type: Usage
Parameter Sets: (All)
Aliases:
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedForReplicationServices, ReservedForMigrationServices, LocalReplicaSource, RemoteReplicaSource, LocalReplicaTarget, RemoteReplicaTarget, LocalReplicaSourceOrTarget, RemoteReplicaSourceOrTarget, DeltaReplicaTarget, ElementComponent, ReservedAsPoolContributer, CompositeVolumeMember, CompositeVirtualDiskMember, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMaximumSize
{{ Fill UseMaximumSize Description }}

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

### -WriteCacheSize
{{ Fill WriteCacheSize Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

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

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS
