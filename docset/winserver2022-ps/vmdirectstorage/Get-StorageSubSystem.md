---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-StorageSubSystem

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByFriendlyName (Default)
```
Get-StorageSubSystem [[-FriendlyName] <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageSubSystem [-UniqueId <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Get-StorageSubSystem [-Name <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageFaultDomain
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageFaultDomain <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFileServer
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-FileServer <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVolume
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-Volume <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPartition
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-Partition <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDisk
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-Disk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByOffloadDataTransferSetting
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-OffloadDataTransferSetting <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorId
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-InitiatorId <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPortal
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-TargetPortal <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPort
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-TargetPort <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByMaskingSet
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-MaskingSet <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePool
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StoragePool <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageNode
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageNode <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageProvider
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageProvider <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
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

### -FileServer
{{ Fill FileServer Description }}

```yaml
Type: CimInstance
Parameter Sets: ByFileServer
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
Accepted values: Healthy, Warning, Unhealthy

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

### -Manufacturer
{{ Fill Manufacturer Description }}

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

### -Model
{{ Fill Model Description }}

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

### -OffloadDataTransferSetting
{{ Fill OffloadDataTransferSetting Description }}

```yaml
Type: CimInstance
Parameter Sets: ByOffloadDataTransferSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition
{{ Fill Partition Description }}

```yaml
Type: CimInstance
Parameter Sets: ByPartition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageFaultDomain
{{ Fill StorageFaultDomain Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageFaultDomain
Aliases: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack, StorageSite

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

### -StorageProvider
{{ Fill StorageProvider Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageProvider
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

### -TargetPortal
{{ Fill TargetPortal Description }}

```yaml
Type: CimInstance
Parameter Sets: ByTargetPortal
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -VirtualDisk
{{ Fill VirtualDisk Description }}

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
{{ Fill Volume Description }}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubSystem

## NOTES

## RELATED LINKS
