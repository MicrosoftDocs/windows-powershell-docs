---
external help file: StoragePool.cdxml-help.xml
Module Name: Storage
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/storage/new-volume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-Volume
---

# New-Volume

## SYNOPSIS
Creates a volume with the specified file system.

## SYNTAX

### ByFriendlyName (Default)
```
New-Volume [-StoragePoolFriendlyName] <String[]> -FriendlyName <String> [-Size <UInt64>]
 -FileSystem <FileSystem> [-AccessPath <String>] [-ResiliencySettingName <String>]
 [-ProvisioningType <ProvisioningType>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>]
 [-StorageTiers <CimInstance[]>] [-StorageTierSizes <UInt64[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-Volume -StoragePoolUniqueId <String[]> -FriendlyName <String> [-Size <UInt64>] -FileSystem <FileSystem>
 [-AccessPath <String>] [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByName
```
New-Volume -StoragePoolName <String[]> -FriendlyName <String> [-Size <UInt64>] -FileSystem <FileSystem>
 [-AccessPath <String>] [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
New-Volume -InputObject <CimInstance[]> -FriendlyName <String> [-Size <UInt64>] -FileSystem <FileSystem>
 [-AccessPath <String>] [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-StorageTiers <CimInstance[]>]
 [-StorageTierSizes <UInt64[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-Volume** cmdlet creates a volume with the specified file system.
The cmdlet manages the creation of the virtual disk with the specified size and resiliency setting, initializes the disk, creates a partition on it and formats the volume with the specified file system, including Cluster Shared Volumes (CSVs).

## EXAMPLES

### Example 1: Create a volume on a mirror space
```
PS C:\> New-Volume -StoragePoolName "CompanyData" -FriendlyName "TestVolume" -Size 10GB -ResiliencySettingName "Mirror" -FileSystem NTFS -AccessPath "M: "-ProvisioningType Fixed
```

This command creates a new storage space in the CompanyData pool using the Mirror resiliency setting and fixed provisioning, and then formats the volume with the NTFS file system and assigns drive letter M.

### Example 2: Create a volume on a new tiered storage space
```
PS C:\>New-Volume -StoragePoolFriendlyName "CompanyData" -FriendlyName "UserData" -AccessPath "M:" -ResiliencySettingName "Mirror" -ProvisioningType "Fixed" -StorageTiers (Get-StorageTier -FriendlyName "*SSD*"), (Get-StorageTier -FriendlyName "*HDD*") -StorageTierSizes 20GB, 80GB -FileSystem NTFS
```

This command creates new storage space in the CompanyData pool using the Mirror resiliency setting, fixed provisioning, a 20 GB SSD storage tier, and an 80 GB HDD storage tier, and then formats the volume with the NTFS file system and assigns drive letter M.

## PARAMETERS

### -AccessPath
Specifies a drive letter or a mount point to assign to the volume.

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

### -AsJob
ps_cimcommon_asjob

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

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

### -FileSystem
Specifies the file system to use for the volume.
The cmdlet formats the volume with the file system you specify.
The acceptable values for this parameter are:

- NTFS 
- ReFS 
- CSVFS_NTFS 
- CSVFS_ReFS

```yaml
Type: FileSystem
Parameter Sets: (All)
Aliases: 
Accepted values: NTFS, ReFS, CSVFS_NTFS, CSVFS_ReFS

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name.
The cmdlet creates the volume with this name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VolumeFriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -NumberOfColumns
Specifies the number of columns to create on the virtual disk.

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

### -PhysicalDiskRedundancy
Specifies the physical disk redundancy value to use during the creation of the virtual disk.
This value represents how many failed physical disks the virtual disk can tolerate without data loss for two-way mirror spaces (1), three-way mirror spaces (2), single-parity spaces (1), and dual parity spaces (2)..

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

### -ProvisioningType
Specifies the type of provisioning. 
The acceptable values for this parameter are: Fixed, or Thin.
Storage spaces that use storage tiers or dual parity must use Fixed provisioning.

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

### -ResiliencySettingName
Specifies the name of the desired resiliency setting, for example, Simple, Mirror, or Parity.

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
Specifies the size of the volume to create.

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

### -StoragePoolFriendlyName
Specifies an array of storage pool friendly names.
The cmdlet creates the volume in the storage pools you specify.

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
Specifies an array of storage pool names.
The cmdlet creates the volume in the storage pools you specify.

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
Specifies an array of unique IDs, as strings.
The cmdlet creates the volume in the storage pools you specify.

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

### -StorageTierSizes
Specifies an array of storage tier sizes.
The cmdlet creates the virtual disk for the volume with the storage tier sizes you specify.

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

### -StorageTiers
Specifies an array of storage tiers.
The cmdlet creates the virtual disk for the volume with the storage tiers you specify.
To obtain a storage tier object, use the New-StorageTier cmdlet.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the InputObject parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/Storage/MSFT_Volume
This cmdlet outputs an object that represents the newly created volume.

## NOTES
* To create a volume on a new storage space with enclosure-awareness enabled (providing resiliency for an entire JBOD enclosure failure), use the **Set-StoragePool** cmdlet with the **-EnclosureAwareDefault $true** parameter to set the storage pool to create storage spaces with enclosure awareness enabled by default.

## RELATED LINKS

