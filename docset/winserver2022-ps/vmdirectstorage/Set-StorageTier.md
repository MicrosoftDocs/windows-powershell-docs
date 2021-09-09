---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-StorageTier

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByUniqueIdNewFriendlyName (Default)
```
Set-StorageTier [-NewFriendlyName <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectDescription
```
Set-StorageTier -InputObject <CimInstance[]> [-Description <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-StorageTier -InputObject <CimInstance[]> [-ProvisioningType <ProvisioningType>]
 [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>] [-FaultDomainAwareness <FaultDomainType>]
 [-ColumnIsolation <FaultDomainType>] [-ResiliencySettingName <String>] [-Usage <StorageTierUsage>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfGroups <UInt16>]
 [-NumberOfColumns <UInt16>] [-Interleave <UInt64>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByObjectNewFriendlyName
```
Set-StorageTier -InputObject <CimInstance[]> [-NewFriendlyName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameNewFriendlyName
```
Set-StorageTier [-NewFriendlyName <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameAttributes
```
Set-StorageTier [-ProvisioningType <ProvisioningType>] [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>]
 [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-ResiliencySettingName <String>] [-Usage <StorageTierUsage>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>]
 [-FriendlyName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdAttributes
```
Set-StorageTier [-ProvisioningType <ProvisioningType>] [-AllocationUnitSize <UInt64>] [-MediaType <MediaType>]
 [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-ResiliencySettingName <String>] [-Usage <StorageTierUsage>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>]
 -UniqueId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDescription
```
Set-StorageTier [-Description <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdDescription
```
Set-StorageTier [-Description <String>] -UniqueId <String> [-CimSession <CimSession[]>]
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

### -AllocationUnitSize
{{ Fill AllocationUnitSize Description }}

```yaml
Type: UInt64
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
{{ Fill Description Description }}

```yaml
Type: String
Parameter Sets: ByObjectDescription, ByFriendlyNameDescription, ByUniqueIdDescription
Aliases:

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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByFriendlyNameNewFriendlyName, ByFriendlyNameAttributes, ByFriendlyNameDescription
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectDescription, ByObjectAttributes, ByObjectNewFriendlyName
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFriendlyName
{{ Fill NewFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByUniqueIdNewFriendlyName, ByObjectNewFriendlyName, ByFriendlyNameNewFriendlyName
Aliases:

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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:

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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases: FaultDomainRedundancy

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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: Thin, Fixed

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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Type: String
Parameter Sets: ByUniqueIdNewFriendlyName, ByUniqueIdAttributes, ByUniqueIdDescription
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
{{ Fill Usage Description }}

```yaml
Type: StorageTierUsage
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: Unknown, Data, ReadCache, WriteCache, DirtyRegionTracking, StripeStateTracking, ValidDataTracking, CacheLines

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
