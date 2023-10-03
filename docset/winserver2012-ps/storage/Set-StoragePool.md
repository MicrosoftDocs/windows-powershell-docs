---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://learn.microsoft.com/powershell/module/storage/set-storagepool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-StoragePool

## SYNOPSIS
Modifies the properties of the specified storage pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-ClearOnDeallocate <Boolean>]
 [-IsPowerProtected <Boolean>] [-NewFriendlyName <String>] [-OtherUsageDescription <String>]
 [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-ThinProvisioningAlertThresholds <UInt16[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_2
```
Set-StoragePool [-InputObject] <CimInstance[]> [-AsJob] [-CimSession <CimSession[]>] [-IsReadOnly <Boolean>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-StoragePool [-FriendlyName] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-EnclosureAwareDefault <Boolean>] [-ProvisioningTypeDefault <ProvisioningType>]
 [-ResiliencySettingNameDefault <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Set-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-EnclosureAwareDefault <Boolean>]
 [-ProvisioningTypeDefault <ProvisioningType>] [-ResiliencySettingNameDefault <String>]
 [-ThrottleLimit <Int32>] -Name <String>
```

### UNNAMED_PARAMETER_SET_5
```
Set-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-ClearOnDeallocate <Boolean>]
 [-IsPowerProtected <Boolean>] [-NewFriendlyName <String>] [-OtherUsageDescription <String>]
 [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-ThinProvisioningAlertThresholds <UInt16[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -Name <String>
```

### UNNAMED_PARAMETER_SET_6
```
Set-StoragePool [-FriendlyName] <String> [-AsJob] [-CimSession <CimSession[]>] [-IsReadOnly <Boolean>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_7
```
Set-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-IsReadOnly <Boolean>] [-ThrottleLimit <Int32>]
 -Name <String>
```

### UNNAMED_PARAMETER_SET_8
```
Set-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-IsReadOnly <Boolean>] [-ThrottleLimit <Int32>]
 -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_9
```
Set-StoragePool [-InputObject] <CimInstance[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>] [-NewFriendlyName <String>]
 [-OtherUsageDescription <String>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>]
 [-ThinProvisioningAlertThresholds <UInt16[]>] [-ThrottleLimit <Int32>] [-Usage <Usage>]
```

### UNNAMED_PARAMETER_SET_10
```
Set-StoragePool [-AsJob] [-CimSession <CimSession[]>] [-EnclosureAwareDefault <Boolean>]
 [-ProvisioningTypeDefault <ProvisioningType>] [-ResiliencySettingNameDefault <String>]
 [-ThrottleLimit <Int32>] -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_11
```
Set-StoragePool [-InputObject] <CimInstance[]> [-AsJob] [-CimSession <CimSession[]>]
 [-EnclosureAwareDefault <Boolean>] [-ProvisioningTypeDefault <ProvisioningType>]
 [-ResiliencySettingNameDefault <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_12
```
Set-StoragePool [-FriendlyName] <String> [-AsJob] [-CimSession <CimSession[]>] [-ClearOnDeallocate <Boolean>]
 [-IsPowerProtected <Boolean>] [-NewFriendlyName <String>] [-OtherUsageDescription <String>]
 [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-ThinProvisioningAlertThresholds <UInt16[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>]
```

## DESCRIPTION
The **Set-StoragePool** cmdlet modifies the properties of the specified storage pool.

## EXAMPLES

### Example 1: Change the friendly name
```
PS C:\>Set-StoragePool -FriendlyName StoragePool -NewFriendlyName StoragePool2
```

This example changes the friendly name of StoragePool to StoragePool2.

### Example 2: Make a read-only storage pool writeable
```
PS C:\>Set-StoragePool -FriendlyName "Storage Pool 1" -IsReadOnly $False
```

This example makes the storage pool named Storage Pool 1 writable when it is in a read-only state.

### Example 3: Set the default resiliency and provisioning settings
```
PS C:\>Set-StoragePool -FriendlyName "Storage Pool 1" -ResiliencySettingsNameDefault Mirror -ProvisioningTypeDefault Thin
```

This example makes any new virtual disks by default use the Mirror resiliency setting and thin provisioning.

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

### -ClearOnDeallocate
Clears all blocks on the physical disks in the storage pool upon deallocation.
Clearing all blocks is more secure, but is much slower to deallocate.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnclosureAwareDefault
Specifies that the storage enclosure used by the storage pool supports SCSI Enclosure Services.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the storage pool on which you want to set attributes.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_11
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsPowerProtected


```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Sets the object to be read-only (`IsReadOnly $true`) or read-write (`IsReadOnly $false`).
**Note**: If the object is set to read-only (`IsReadOnly $true`), the object must be set to read-write (`IsReadOnly $false`) before using this cmdlet to set the **PartitionStyle** parameter.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage pool on which you want to set attributes.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies the new friendly name for the storage pool.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies the OtherUsageDescription for the storage pool.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: NewOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningTypeDefault
Specifies the default type of provisioning to use for virtual disks created in the specified storage pool.
The acceptable values for this parameter are: **Fixed** or **Thin**.

```yaml
Type: ProvisioningType
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingNameDefault
Specifies the default resiliency setting (also known as storage layout) to use for virtual disks the created in the specified storage pool.
The supported resiliency settings vary by storage subsystem.
Acceptable values for the Storage Spaces subsystem are Mirror, Parity, and Simple.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetireMissingPhysicalDisks
Specifies that Windows should set the Usage property of physical disks missing from a storage pool to Retired.

```yaml
Type: RetireMissingPhysicalDisks
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThinProvisioningAlertThresholds
Specifies how full a storage pool must get (in percent) before an alert is generated to add physical disks to the storage pool to support thinly provisioned virtual disks.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: 70
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

### -UniqueId
Specifies the UniqueID of the storage pool for which you want to set attributes.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_10
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Specifies the usage setting for the storage pool.
The acceptable values for this parameter are:Other, ReservedAsDeltaReplicaContainer, ReservedForComputerSystem, ReservedForLocalReplicationServices, ReservedForMigrationServices, ReservedForRemoteReplicationServices, ReservedForSparing, and Unrestricted.

```yaml
Type: Usage
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_12
Aliases: NewUsage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe one or more MSFT_StoragePool objects to the InputObject parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

[New-StoragePool](./New-StoragePool.md)

[Remove-StoragePool](./Remove-StoragePool.md)

