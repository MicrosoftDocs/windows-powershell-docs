---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-VirtualDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByUniqueId (Default)
```
Set-VirtualDisk [-NewFriendlyName <String>] [-Usage <Usage>] [-OtherUsageDescription <String>]
 -UniqueId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectProperties
```
Set-VirtualDisk [-InputObject] <CimInstance[]> [-ProvisioningType <ProvisioningType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-MaxIops <UInt64>]
 [-MaxIoBandwidth <UInt64>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-VirtualDisk [-InputObject] <CimInstance[]> [-IsManualAttach <Boolean>] [-StorageNodeName <String>]
 [-Access <Access>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObject
```
Set-VirtualDisk [-InputObject] <CimInstance[]> [-NewFriendlyName <String>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByName
```
Set-VirtualDisk [-NewFriendlyName <String>] [-Usage <Usage>] [-OtherUsageDescription <String>] -Name <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyName
```
Set-VirtualDisk [-NewFriendlyName <String>] [-Usage <Usage>] [-OtherUsageDescription <String>]
 [-FriendlyName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdProperties
```
Set-VirtualDisk -UniqueId <String> [-ProvisioningType <ProvisioningType>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-MaxIops <UInt64>] [-MaxIoBandwidth <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdAttributes
```
Set-VirtualDisk -UniqueId <String> [-IsManualAttach <Boolean>] [-StorageNodeName <String>] [-Access <Access>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameProperties
```
Set-VirtualDisk [-FriendlyName] <String> [-ProvisioningType <ProvisioningType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-MaxIops <UInt64>]
 [-MaxIoBandwidth <UInt64>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameAttributes
```
Set-VirtualDisk [-FriendlyName] <String> [-IsManualAttach <Boolean>] [-StorageNodeName <String>]
 [-Access <Access>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameProperties
```
Set-VirtualDisk -Name <String> [-ProvisioningType <ProvisioningType>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-MaxIops <UInt64>] [-MaxIoBandwidth <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameAttributes
```
Set-VirtualDisk -Name <String> [-IsManualAttach <Boolean>] [-StorageNodeName <String>] [-Access <Access>]
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

### -Access
{{ Fill Access Description }}

```yaml
Type: Access
Parameter Sets: ByObjectAttributes, ByUniqueIdAttributes, ByFriendlyNameAttributes, ByNameAttributes
Aliases:
Accepted values: Unknown, Readable, Writeable, ReadWrite, WriteOnce

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

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByFriendlyName, ByFriendlyNameProperties, ByFriendlyNameAttributes
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
Parameter Sets: ByObjectProperties, ByObjectAttributes, ByObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsManualAttach
{{ Fill IsManualAttach Description }}

```yaml
Type: Boolean
Parameter Sets: ByObjectAttributes, ByUniqueIdAttributes, ByFriendlyNameAttributes, ByNameAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxIoBandwidth
{{ Fill MaxIoBandwidth Description }}

```yaml
Type: UInt64
Parameter Sets: ByObjectProperties, ByUniqueIdProperties, ByFriendlyNameProperties, ByNameProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxIops
{{ Fill MaxIops Description }}

```yaml
Type: UInt64
Parameter Sets: ByObjectProperties, ByUniqueIdProperties, ByFriendlyNameProperties, ByNameProperties
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
Type: String
Parameter Sets: ByName, ByNameProperties, ByNameAttributes
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
Parameter Sets: ByUniqueId, ByObject, ByName, ByFriendlyName
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
Parameter Sets: ByObjectProperties, ByUniqueIdProperties, ByFriendlyNameProperties, ByNameProperties
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
Parameter Sets: ByUniqueId, ByObject, ByName, ByFriendlyName
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
Parameter Sets: ByObjectProperties, ByUniqueIdProperties, ByFriendlyNameProperties, ByNameProperties
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
Parameter Sets: ByObjectProperties, ByUniqueIdProperties, ByFriendlyNameProperties, ByNameProperties
Aliases:
Accepted values: Thin, Fixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageNodeName
{{ Fill StorageNodeName Description }}

```yaml
Type: String
Parameter Sets: ByObjectAttributes, ByUniqueIdAttributes, ByFriendlyNameAttributes, ByNameAttributes
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
Parameter Sets: ByUniqueId, ByUniqueIdProperties, ByUniqueIdAttributes
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
Parameter Sets: ByUniqueId, ByObject, ByName, ByFriendlyName
Aliases:
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedForReplicationServices, ReservedForMigrationServices, LocalReplicaSource, RemoteReplicaSource, LocalReplicaTarget, RemoteReplicaTarget, LocalReplicaSourceOrTarget, RemoteReplicaSourceOrTarget, DeltaReplicaTarget, ElementComponent, ReservedAsPoolContributer, CompositeVolumeMember, CompositeVirtualDiskMember, ReservedForSparing

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
