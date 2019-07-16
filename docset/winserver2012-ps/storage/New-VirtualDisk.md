---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 0A351B38-1E4B-451C-A66B-EF97683646F4
manager: dansimp
---

# New-VirtualDisk

## SYNOPSIS
Creates a new virtual disk in the specified storage pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VirtualDisk [-StoragePoolFriendlyName] <String[]> [-AsJob] [-AutoNumberOfColumns]
 [-CimSession <CimSession[]>] [-Interleave <UInt64>] [-IsEnclosureAware <Boolean>] [-NumberOfColumns <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-OtherUsageDescription <String>] [-PhysicalDiskRedundancy <UInt16>]
 [-PhysicalDisksToUse <CimInstance[]>] [-ProvisioningType <ProvisioningType>] [-ResiliencySettingName <String>]
 [-Size <UInt64>] [-ThrottleLimit <Int32>] [-Usage <Usage>] [-UseMaximumSize] -FriendlyName <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-VirtualDisk [-AsJob] [-AutoNumberOfColumns] [-CimSession <CimSession[]>] [-Interleave <UInt64>]
 [-IsEnclosureAware <Boolean>] [-NumberOfColumns <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-OtherUsageDescription <String>] [-PhysicalDiskRedundancy <UInt16>] [-PhysicalDisksToUse <CimInstance[]>]
 [-ProvisioningType <ProvisioningType>] [-ResiliencySettingName <String>] [-Size <UInt64>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] [-UseMaximumSize] -FriendlyName <String>
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_3
```
New-VirtualDisk [-AsJob] [-AutoNumberOfColumns] [-CimSession <CimSession[]>] [-Interleave <UInt64>]
 [-IsEnclosureAware <Boolean>] [-NumberOfColumns <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-OtherUsageDescription <String>] [-PhysicalDiskRedundancy <UInt16>] [-PhysicalDisksToUse <CimInstance[]>]
 [-ProvisioningType <ProvisioningType>] [-ResiliencySettingName <String>] [-Size <UInt64>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] [-UseMaximumSize] -FriendlyName <String> -StoragePoolName <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-VirtualDisk [-AsJob] [-AutoNumberOfColumns] [-CimSession <CimSession[]>] [-Interleave <UInt64>]
 [-IsEnclosureAware <Boolean>] [-NumberOfColumns <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-OtherUsageDescription <String>] [-PhysicalDiskRedundancy <UInt16>] [-PhysicalDisksToUse <CimInstance[]>]
 [-ProvisioningType <ProvisioningType>] [-ResiliencySettingName <String>] [-Size <UInt64>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] [-UseMaximumSize] -FriendlyName <String>
 -StoragePoolUniqueId <String[]>
```

## DESCRIPTION
The **New-VirtualDisk** cmdlet creates a new virtual disk in the specified storage pool.

## EXAMPLES

### Example 1: Creating a 100 GB virtual disk using default settings
```
PS C:\>New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName UserData -Size 100GB
```

This example creates a virtual disk named UserData from the storage pool named CompanyData that is 100GB in size, using the storage pool default settings for unspecified parameters.

### Example 2: Creating a thinly-provisioned mirror
```
PS C:\>New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName DataWarehouse -ResiliencySettingName Mirror -Size 42TB -ProvisioningType Thin
```

This example creates a virtual disk named DataWarehouse, which is 42TB in size, uses the Mirror resiliency setting, and is thinly provisioned.

### Example 3: Creating a three-way mirror
```
PS C:\>New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName BusinessCritical -ResiliencySettingName Mirror -NumberOfDataCopies 3 -Size 42TB -ProvisioningType Thin
```

This example creates a 42 TB thinly-provisioned virtual disk on the Storage Spaces subsystem, using the Mirror resiliency setting with three data copies.
This creates a three-way mirror that is capable of tolerating two disk failures).

### Example 4: Creating a two-column mirror
```
PS C:\>New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName BusinessCritical -ResiliencySettingName Mirror - -Size 42TB -ProvisioningType Thin -NumberOfColumns 2
```

This example creates a thinly-provisioned virtual disk on the Storage Spaces subsystem that uses two columns, regardless of how many physical disks are in the storage pool above the two-disk minimum for a two-way mirror.

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

### -AutoNumberOfColumns
Specifies that the number of columns used by the virtual disk should be automatically determined.
Columns represent the number of underlying physical disks across which one stripe of data for a virtual disk is written.

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

### -FriendlyName
Specifies the friendly name for the virtual disk.
The friendly name is not required to be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskFriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts a StoragePool object as input, specifying in which storage pool to create the virtual disk.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Interleave
Specifies the interleave value to use during the creation of a virtual disk.
The interleave value represents the number of bytes that is written to a single physical disk.
Thus Interleave * NumberOfColumns will yield the size of one stripe of user data.

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

### -IsEnclosureAware
Specifies that the enclosure supports SCSI Enclosure Services (SES), which is utilized for providing things like Slot location for a physical disk, as well as to manage LEDs on the disks for visual identification.

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

### -NumberOfColumns
Specifies the number of columns to use when allocating the virtual disk.

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

### -NumberOfDataCopies
Specifies the number of data copies to create.
Specify 2 to create a two-way mirror, or 3 to specify a three-way mirror.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies an OtherUsageDescription string for the virtual disk.
You can use the **OtherUsageDescription** parameter only if you set the **Usage** parameter to Other or do not include the **Usage** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDiskRedundancy
Specifies the physical disk redundancy value to use during the creation of a virtual disk.
This value represents how many failed physical disks the virtual disk can tolerate without data loss.

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

### -PhysicalDisksToUse
Specifies an array of one or more PhysicalDisk objects.
The PhysicalDisk objects represent the specific physical disks on which to create this virtual disk.

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

### -ProvisioningType
Specifies the type of provisioning.
The acceptable values for this parameter are:**Fixed**, or **Thin**.

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

### -ResiliencySettingName
Specifies the resiliency setting (storage layout) to use for the virtual disk.
Acceptable values vary by storage subsystem.

Allowed values for the Storage Spaces subsystem are: **Simple**, **Mirror**, or **Parity**.

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
Specifies the size of the virtual disk to create.
The default unit is Bytes; to specify a different unit, enter the size followed by one of the following unit values, with no spaces: Bytes, KB, MB, GB, or TB.

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
Specifies the friendly name of the storage pool in which to create the virtual disk.
Enter a friendly name, or use wildcard characters to enter a name pattern.

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

### -StoragePoolName
Specifies the name of the storage pool in which to create the virtual disk.
Enter the name of the storage pool provided by the Storage Management Provider, or use wildcard characters to enter a name pattern.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoragePoolUniqueId
Specifies the ID of the storage pool in which to create the virtual disk Enter an ID or use wildcard characters to enter a pattern.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: StoragePoolId

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
Specifies the intended usage of the virtual disk.
You can specify one of the predefined descriptions, or use the default value (Other) and instead use the OtherUsageDescription parameter to specify a custom value.

```yaml
Type: Usage
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Other
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMaximumSize
Creates a virtual disk with the maximum size possible given the available storage pool space and specified parameters.

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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe an MSFT_StoragePool object to the InputObject parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The New-VirtualDisk cmdlet returns an object that represents the newly created virtual disk.

## NOTES

## RELATED LINKS

[Add-VirtualDiskToMaskingSet](./Add-VirtualDiskToMaskingSet.md)

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-MaskingSet](./New-MaskingSet.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)

