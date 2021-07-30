---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/new-storagepool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-StoragePool

## SYNOPSIS
Creates a new storage pool using a group of physical disks, and a specific storage subsystem exposed by a storage provider.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-StoragePool [-StorageSubSystemFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-EnclosureAwareDefault <Boolean>] [-LogicalSectorSizeDefault <UInt64>] [-OtherUsageDescription <String>]
 [-ProvisioningTypeDefault <ProvisioningType>] [-ResiliencySettingNameDefault <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -FriendlyName <String> -PhysicalDisks <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_2
```
New-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-EnclosureAwareDefault <Boolean>]
 [-LogicalSectorSizeDefault <UInt64>] [-OtherUsageDescription <String>]
 [-ProvisioningTypeDefault <ProvisioningType>] [-ResiliencySettingNameDefault <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -FriendlyName <String> -PhysicalDisks <CimInstance[]>
 -StorageSubSystemUniqueId <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
New-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-EnclosureAwareDefault <Boolean>]
 [-LogicalSectorSizeDefault <UInt64>] [-OtherUsageDescription <String>]
 [-ProvisioningTypeDefault <ProvisioningType>] [-ResiliencySettingNameDefault <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -FriendlyName <String> -InputObject <CimInstance[]>
 -PhysicalDisks <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-EnclosureAwareDefault <Boolean>]
 [-LogicalSectorSizeDefault <UInt64>] [-OtherUsageDescription <String>]
 [-ProvisioningTypeDefault <ProvisioningType>] [-ResiliencySettingNameDefault <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -FriendlyName <String> -PhysicalDisks <CimInstance[]>
 -StorageSubSystemName <String[]>
```

## DESCRIPTION
The **New-StoragePool** cmdlet creates a new storage pool using a group of physical disks, and a specific storage subsystem exposed by a storage provider.

## EXAMPLES

### Example 1: Create a new storage pool using Storage Spaces
```
This line uses the **Get-PhysicalDisk** cmdlet to get all PhysicalDisk objects than are not yet in a (concrete) storage pool, and assigns the array of objects to the $PhysicalDisks variable.
PS C:\>$PhysicalDisks = (Get-PhysicalDisk -CanPool $True)

This line creates a new storage pool using the $PhysicalDisks variable to specify the disks to include from the Storage Spaces subsystem (specified with a wildcard * to remove the need to modify the friendly name for different computers).
PS C:\>New-StoragePool -FriendlyName CompanyData -StorageSubsystemFriendlyName "Storage Spaces*" -PhysicalDisks $PhysicalDisks
```

This example creates a new storage pool named CompanyData using the Storage Spaces subsytem, using the minimum parameters, and assuming that there are no other storage subsystems attached to the computer that have available disks.

### Example 2: Create a new pool and set defaults for virtual disks
```
PS C:\>$PhysicalDisks = (Get-PhysicalDisk -CanPool $True) 



PS C:\>New-StoragePool -FriendlyName CompanyData -StorageSubsystemFriendlyName "Storage Spaces*" -PhysicalDisks $PhysicalDisks -ResiliencySettingNameDefault Mirror -ProvisioningTypeDefault Thin -Verbose
```

This example creates a new storage pool named CompanyData using the Storage Spaces subsystem and sets default values for virtual disk creation.

### Example 3: Create a new storage pool, virtual disk, partition, and volume
```
This line gets the storage subsystem object for the Storage Spaces subsystem, passes it to the **Get-PhysicalDisk** cmdlet, which then gets the physical disks in the specified subsystem that are available to add to a storage pool, and assigns these disks to the $PhysicalDisks variable.
PS C:\>$PhysicalDisks = Get-StorageSubSystem -FriendlyName "Storage Spaces*" | Get-PhysicalDisk -CanPool $True

This line creates a new storage pool using the physical disks in the $PhysicalDisks variable, and then passes the new storage pool down the pipeline.
PS C:\>New-StoragePool -FriendlyName CompanyData -StorageSubsystemFriendlyName "Storage Spaces*" -PhysicalDisks $PhysicalDisks |

This line creates a new virtual disk on the passed in storage pool, and then passes the new virtual disk down the pipeline.
PS C:\>New-VirtualDisk -FriendlyName UserData -Size 100GB -ProvisioningType Thin |

This line initializes the disk that was passed in, and then passes the disk down the pipeline.
PS C:\>Initialize-Disk -PassThru |

This line creates a new partition on the disk that was passed in, assigns it the next available drive letter, and then passes the partition down the pipeline.
PS C:\>New-Partition -AssignDriveLetter -UseMaximumSize |

This line formats the partition that was passed in.
PS C:\>Format-Volume
```

This example creates a new storage pool, and then makes use of the pipeline to create a new virtual disk in the pool, initialize the disk, create a new partition on the disk, and then format the new partition (volume).

## PARAMETERS

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -EnclosureAwareDefault
Specifies the default allocation policy for virtual disks created in an enclosure-aware storage pool.
For example, an enclosure-aware subsystem could balance each data copy of the virtual disk across multiple physical enclosures such that each enclosure contains a full data copy of the virtual disk.

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

### -FriendlyName
Specifies a friendly name for the storage pool to be created.
The friendly name may be defined by a user and is not guaranteed to be unique.

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
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogicalSectorSizeDefault
Specifies the default logical sector size to use for virtual disks created in this pool.
Valid logical sector size values (in bytes) for virtual disks created by using the Storage Spaces subsystem are 512 and 4096.

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

### -OtherUsageDescription
Specifies the usage description for the storage pool.

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
Accepts one or more PhysicalDisk objects as input.
The Physical Disk CIM objects represent the physical disks to be added to the storage pool.

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
Specifies the default type of provisioning for virtual disks created in this pool.
The acceptable values for this parameter are: Unknown, Fixed or Thin.

```yaml
Type: ProvisioningType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingNameDefault
Specifies the default resiliency setting name for virtual disks created in this pool.

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
Specifies the friendly name of the storage subsystem on which you want to create the storage pool.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemName
Specifies the name of the storage subsystem (provided by the Storage Management) on which you want to create the storage pool.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
Specifies the ID of the storage subsystem on which you want to create the storage pool

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: StorageSubsystemId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Usage
Specifies the usage setting for the storage pool.
The acceptable values for this parameter are:Other, ReservedAsDeltaReplicaContainer, ReservedForComputerSystem, ReservedForLocalReplicationServices, ReservedForMigrationServices, ReservedForRemoteReplicationServices, ReservedForSparing, and Unrestricted.

```yaml
Type: Usage
Parameter Sets: (All)
Aliases: StoragePoolUsage

Required: False
Position: Named
Default value: Other
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe one or more MSFT_PhysicalDisk objects to the PhysicalDisks parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
This cmdlet returns an object representing the newly created storage pool.

## NOTES

## RELATED LINKS

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-StorageSubsystem](./Get-StorageSubsystem.md)

[Remove-StoragePool](./Remove-StoragePool.md)

[Set-StoragePool](./Set-StoragePool.md)

