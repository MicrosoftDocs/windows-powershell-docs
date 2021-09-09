---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# New-Volume

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByStoragePool (Default)
```
New-Volume [[-StoragePool] <CimInstance>] -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-NumberOfGroups <UInt16>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-StorageFaultDomainsToUseFriendlyNames <String[]>] [-StorageTiers <CimInstance[]>]
 [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>]
 [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePoolFriendlyName
```
New-Volume -StoragePoolFriendlyName <String> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-NumberOfGroups <UInt16>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-StorageFaultDomainsToUseFriendlyNames <String[]>] [-StorageTiers <CimInstance[]>]
 [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>]
 [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePoolName
```
New-Volume -StoragePoolName <String> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-NumberOfGroups <UInt16>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-StorageFaultDomainsToUseFriendlyNames <String[]>] [-StorageTiers <CimInstance[]>]
 [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>]
 [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePoolUniqueId
```
New-Volume -StoragePoolUniqueId <String> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>] [-NumberOfColumns <UInt16>]
 [-NumberOfGroups <UInt16>] [-StorageFaultDomainsToUse <CimInstance[]>]
 [-StorageFaultDomainsToUseFriendlyNames <String[]>] [-StorageTiers <CimInstance[]>]
 [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>] [-WriteCacheSize <UInt64>]
 [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByDisk
```
New-Volume [-Disk] <CimInstance> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDiskNumber
```
New-Volume [-DiskNumber] <UInt32> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDiskPath
```
New-Volume -DiskPath <String> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDiskUniqueId
```
New-Volume -DiskUniqueId <String> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
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

### -AccessPath
{{ Fill AccessPath Description }}

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

### -AllocationUnitSize
{{ Fill AllocationUnitSize Description }}

```yaml
Type: UInt32
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

### -Disk
{{ Fill Disk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DiskNumber
{{ Fill DiskNumber Description }}

```yaml
Type: UInt32
Parameter Sets: ByDiskNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskPath
{{ Fill DiskPath Description }}

```yaml
Type: String
Parameter Sets: ByDiskPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskUniqueId
{{ Fill DiskUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByDiskUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriveLetter
{{ Fill DriveLetter Description }}

```yaml
Type: Char
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
{{ Fill FileSystem Description }}

```yaml
Type: FileSystemType
Parameter Sets: (All)
Aliases:
Accepted values: NTFS, ReFS, CSVFS_NTFS, CSVFS_ReFS

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
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaType
{{ Fill MediaType Description }}

```yaml
Type: MediaType
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFaultDomainsToUseFriendlyNames
{{ Fill StorageFaultDomainsToUseFriendlyNames Description }}

```yaml
Type: String[]
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
{{ Fill StoragePool Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
{{ Fill StoragePoolFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByStoragePoolFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolName
{{ Fill StoragePoolName Description }}

```yaml
Type: String
Parameter Sets: ByStoragePoolName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolUniqueId
{{ Fill StoragePoolUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByStoragePoolUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierFriendlyNames
{{ Fill StorageTierFriendlyNames Description }}

```yaml
Type: String[]
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTiers
{{ Fill StorageTiers Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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

### -UseMaximumSize
{{ Fill UseMaximumSize Description }}

```yaml
Type: SwitchParameter
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
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

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
