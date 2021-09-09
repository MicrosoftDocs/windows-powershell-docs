---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-PhysicalDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByUniqueId (Default)
```
Get-PhysicalDisk [-UniqueId <String>] [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByObjectId
```
Get-PhysicalDisk [-ObjectId <String>] [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByDeviceNumber
```
Get-PhysicalDisk [-DeviceNumber <String>] [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByName
```
Get-PhysicalDisk [[-FriendlyName] <String>] [[-SerialNumber] <String>] [-Usage <PhysicalDiskUsage>]
 [-Description <String>] [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>]
 [-HealthStatus <PhysicalDiskHealthStatus>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByInputObject
```
Get-PhysicalDisk -InputObject <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageSubsystem
```
Get-PhysicalDisk -StorageSubsystem <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageEnclosure
```
Get-PhysicalDisk -StorageEnclosure <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageScaleUnit
```
Get-PhysicalDisk -StorageScaleUnit <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageChassis
```
Get-PhysicalDisk -StorageChassis <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageRack
```
Get-PhysicalDisk -StorageRack <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageSite
```
Get-PhysicalDisk -StorageSite <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageNode
```
Get-PhysicalDisk -StorageNode <CimInstance> [-PhysicallyConnected] [-Usage <PhysicalDiskUsage>]
 [-Description <String>] [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>]
 [-HealthStatus <PhysicalDiskHealthStatus>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStoragePool
```
Get-PhysicalDisk -StoragePool <CimInstance> [-HasMetadata] [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-PhysicalDisk -VirtualDisk <CimInstance> [-VirtualRangeMin <UInt64>] [-VirtualRangeMax <UInt64>]
 [-HasAllocations <Boolean>] [-SelectedForUse <Boolean>] [-NoRedundancy] [-HasMetadata]
 [-Usage <PhysicalDiskUsage>] [-Description <String>] [-Manufacturer <String>] [-Model <String>]
 [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>] [-CimSession <CimSession>]
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

### -CanPool
{{ Fill CanPool Description }}

```yaml
Type: Boolean
Parameter Sets: ByUniqueId, ByObjectId, ByDeviceNumber, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageScaleUnit, ByStorageChassis, ByStorageRack, ByStorageSite, ByStorageNode, ByStoragePool, ByVirtualDisk
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
Type: CimSession
Parameter Sets: (All)
Aliases:

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
Parameter Sets: ByUniqueId, ByObjectId, ByDeviceNumber, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageScaleUnit, ByStorageChassis, ByStorageRack, ByStorageSite, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNumber
{{ Fill DeviceNumber Description }}

```yaml
Type: String
Parameter Sets: ByDeviceNumber
Aliases:

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
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HasAllocations
{{ Fill HasAllocations Description }}

```yaml
Type: Boolean
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HasMetadata
{{ Fill HasMetadata Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthStatus
{{ Fill HealthStatus Description }}

```yaml
Type: PhysicalDiskHealthStatus
Parameter Sets: ByUniqueId, ByObjectId, ByDeviceNumber, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageScaleUnit, ByStorageChassis, ByStorageRack, ByStorageSite, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:
Accepted values: Healthy, Warning, Unhealthy, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Manufacturer
{{ Fill Manufacturer Description }}

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObjectId, ByDeviceNumber, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageScaleUnit, ByStorageChassis, ByStorageRack, ByStorageSite, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Model
{{ Fill Model Description }}

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObjectId, ByDeviceNumber, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageScaleUnit, ByStorageChassis, ByStorageRack, ByStorageSite, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRedundancy
{{ Fill NoRedundancy Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
{{ Fill ObjectId Description }}

```yaml
Type: String
Parameter Sets: ByObjectId
Aliases: PhysicalDiskObjectId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicallyConnected
{{ Fill PhysicallyConnected Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectedForUse
{{ Fill SelectedForUse Description }}

```yaml
Type: Boolean
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerialNumber
{{ Fill SerialNumber Description }}

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: 1
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

Required: True
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

Required: True
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

Required: True
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

Required: True
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

Required: True
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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSite
{{ Fill StorageSite Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageSite
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubsystem
{{ Fill StorageSubsystem Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubsystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UniqueId
{{ Fill UniqueId Description }}

```yaml
Type: String
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Usage
{{ Fill Usage Description }}

```yaml
Type: PhysicalDiskUsage
Parameter Sets: ByUniqueId, ByObjectId, ByDeviceNumber, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageScaleUnit, ByStorageChassis, ByStorageRack, ByStorageSite, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:
Accepted values: Unknown, AutoSelect, ManualSelect, HotSpare, Retired, Journal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
{{ Fill VirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualRangeMax
{{ Fill VirtualRangeMax Description }}

```yaml
Type: UInt64
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualRangeMin
{{ Fill VirtualRangeMin Description }}

```yaml
Type: UInt64
Parameter Sets: ByVirtualDisk
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

### System.String

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
