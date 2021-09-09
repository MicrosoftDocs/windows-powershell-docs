---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-StorageSubSystem

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByUniqueIdDescription (Default)
```
Set-StorageSubSystem [-Description <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectSetAttributes
```
Set-StorageSubSystem [-InputObject] <CimInstance[]> [-AutomaticClusteringEnabled <Boolean>]
 [-VirtualDiskRepairQueueDepth <RepairPriority>] [-FaultDomainAwarenessDefault <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectDescription
```
Set-StorageSubSystem [-InputObject] <CimInstance[]> [-Description <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameDescription
```
Set-StorageSubSystem [-Description <String>] -Name <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDescription
```
Set-StorageSubSystem [-Description <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdSetAttributes
```
Set-StorageSubSystem -UniqueId <String> [-AutomaticClusteringEnabled <Boolean>]
 [-VirtualDiskRepairQueueDepth <RepairPriority>] [-FaultDomainAwarenessDefault <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameSetAttributes
```
Set-StorageSubSystem [-FriendlyName] <String> [-AutomaticClusteringEnabled <Boolean>]
 [-VirtualDiskRepairQueueDepth <RepairPriority>] [-FaultDomainAwarenessDefault <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameSetAttributes
```
Set-StorageSubSystem -Name <String> [-AutomaticClusteringEnabled <Boolean>]
 [-VirtualDiskRepairQueueDepth <RepairPriority>] [-FaultDomainAwarenessDefault <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -AutomaticClusteringEnabled
{{ Fill AutomaticClusteringEnabled Description }}

```yaml
Type: Boolean
Parameter Sets: ByObjectSetAttributes, ByUniqueIdSetAttributes, ByFriendlyNameSetAttributes, ByNameSetAttributes
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

### -Description
{{ Fill Description Description }}

```yaml
Type: String
Parameter Sets: ByUniqueIdDescription, ByObjectDescription, ByNameDescription, ByFriendlyNameDescription
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
Parameter Sets: ByObjectSetAttributes, ByUniqueIdSetAttributes, ByFriendlyNameSetAttributes, ByNameSetAttributes
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
Parameter Sets: ByFriendlyNameDescription, ByFriendlyNameSetAttributes
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
Parameter Sets: ByObjectSetAttributes, ByObjectDescription
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: ByNameDescription, ByNameSetAttributes
Aliases:

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

### -UniqueId
{{ Fill UniqueId Description }}

```yaml
Type: String
Parameter Sets: ByUniqueIdDescription, ByUniqueIdSetAttributes
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDiskRepairQueueDepth
{{ Fill VirtualDiskRepairQueueDepth Description }}

```yaml
Type: RepairPriority
Parameter Sets: ByObjectSetAttributes, ByUniqueIdSetAttributes, ByFriendlyNameSetAttributes, ByNameSetAttributes
Aliases: VirtualDiskRepairPriority
Accepted values: VeryLow, Low, Medium, High, VeryHigh

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
