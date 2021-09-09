---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-StoragePool

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByUniqueId (Default)
```
Set-StoragePool [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>]
 [-RepairPolicy <RepairPolicy>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ThinProvisioningAlertThresholds <UInt16[]>] -UniqueId <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-StoragePool [-InputObject] <CimInstance[]> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectDefaults
```
Set-StoragePool [-InputObject] <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByObject
```
Set-StoragePool [-InputObject] <CimInstance[]> [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>]
 [-IsPowerProtected <Boolean>] [-RepairPolicy <RepairPolicy>]
 [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>] [-OtherUsageDescription <String>]
 [-ThinProvisioningAlertThresholds <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyName
```
Set-StoragePool [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>]
 [-RepairPolicy <RepairPolicy>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ThinProvisioningAlertThresholds <UInt16[]>] [-FriendlyName] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Set-StoragePool [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>]
 [-RepairPolicy <RepairPolicy>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ThinProvisioningAlertThresholds <UInt16[]>] -Name <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdAttributes
```
Set-StoragePool -UniqueId <String> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdDefaults
```
Set-StoragePool -UniqueId <String> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByNameAttributes
```
Set-StoragePool -Name <String> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByNameDefaults
```
Set-StoragePool -Name <String> [-ProvisioningTypeDefault <ProvisioningType>] [-MediaTypeDefault <MediaType>]
 [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyNameAttributes
```
Set-StoragePool [-FriendlyName] <String> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDefaults
```
Set-StoragePool [-FriendlyName] <String> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
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

### -AutoWriteCacheSize
{{ Fill AutoWriteCacheSize Description }}

```yaml
Type: Boolean
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
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

### -ClearOnDeallocate
{{ Fill ClearOnDeallocate Description }}

```yaml
Type: Boolean
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnclosureAwareDefault
{{ Fill EnclosureAwareDefault Description }}

```yaml
Type: Boolean
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaultDomainAwarenessDefault
{{ Fill FaultDomainAwarenessDefault Description }}

```yaml
Type: FaultDomainType
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
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
Parameter Sets: ByFriendlyName, ByFriendlyNameAttributes, ByFriendlyNameDefaults
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
Parameter Sets: ByObjectAttributes, ByObjectDefaults, ByObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsPowerProtected
{{ Fill IsPowerProtected Description }}

```yaml
Type: Boolean
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
{{ Fill IsReadOnly Description }}

```yaml
Type: Boolean
Parameter Sets: ByObjectAttributes, ByUniqueIdAttributes, ByNameAttributes, ByFriendlyNameAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaTypeDefault
{{ Fill MediaTypeDefault Description }}

```yaml
Type: MediaType
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases:
Accepted values: Unspecified, HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: ByName, ByNameAttributes, ByNameDefaults
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewFriendlyName
{{ Fill NewFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
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
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: NewOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningTypeDefault
{{ Fill ProvisioningTypeDefault Description }}

```yaml
Type: ProvisioningType
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases:
Accepted values: Unknown, Thin, Fixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepairPolicy
{{ Fill RepairPolicy Description }}

```yaml
Type: RepairPolicy
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases:
Accepted values: Sequential, Parallel

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingNameDefault
{{ Fill ResiliencySettingNameDefault Description }}

```yaml
Type: String
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetireMissingPhysicalDisks
{{ Fill RetireMissingPhysicalDisks Description }}

```yaml
Type: RetireMissingPhysicalDisks
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases:
Accepted values: Auto, Always, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThinProvisioningAlertThresholds
{{ Fill ThinProvisioningAlertThresholds Description }}

```yaml
Type: UInt16[]
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
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
Parameter Sets: ByUniqueId, ByUniqueIdAttributes, ByUniqueIdDefaults
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
Type: Usage
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: NewUsage
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedAsDeltaReplicaContainer, ReservedForMigrationServices, ReservedForLocalReplicationServices, ReservedForRemoteReplicationServices, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteCacheSizeDefault
{{ Fill WriteCacheSizeDefault Description }}

```yaml
Type: UInt64
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
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

### Microsoft.Management.Infrastructure.CimInstance[]

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
