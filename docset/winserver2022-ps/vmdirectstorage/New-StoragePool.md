---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# New-StoragePool

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByFriendlyName (Default)
```
New-StoragePool [-StorageSubSystemFriendlyName] <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-Version <Version>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-StoragePool -StorageSubSystemUniqueId <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-Version <Version>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-StoragePool -StorageSubSystemName <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-Version <Version>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-StoragePool -InputObject <CimInstance[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-Version <Version>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -EnclosureAwareDefault
{{ Fill EnclosureAwareDefault Description }}

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

### -FaultDomainAwarenessDefault
{{ Fill FaultDomainAwarenessDefault Description }}

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
Aliases: StoragePoolFriendlyName

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

### -LogicalSectorSizeDefault
{{ Fill LogicalSectorSizeDefault Description }}

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

### -MediaTypeDefault
{{ Fill MediaTypeDefault Description }}

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

### -OtherUsageDescription
{{ Fill OtherUsageDescription Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: StoragePoolOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisks
{{ Fill PhysicalDisks Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningTypeDefault
{{ Fill ProvisioningTypeDefault Description }}

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

### -ResiliencySettingNameDefault
{{ Fill ResiliencySettingNameDefault Description }}

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

### -StorageSubSystemFriendlyName
{{ Fill StorageSubSystemFriendlyName Description }}

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

### -StorageSubSystemName
{{ Fill StorageSubSystemName Description }}

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

### -StorageSubSystemUniqueId
{{ Fill StorageSubSystemUniqueId Description }}

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StorageSubsystemId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Aliases: StoragePoolUsage
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedAsDeltaReplicaContainer, ReservedForMigrationServices, ReservedForLocalReplicationServices, ReservedForRemoteReplicationServices, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
{{ Fill Version Description }}

```yaml
Type: Version
Parameter Sets: (All)
Aliases:
Accepted values: WindowsServer2012, WindowsServer2012R2, WindowsServer2016, WindowsServer2016RS3, WindowsServer2019, WindowsServer2022

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
