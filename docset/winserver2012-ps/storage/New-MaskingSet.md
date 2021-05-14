---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/new-maskingset?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-MaskingSet

## SYNOPSIS
Creates a new masking set.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-MaskingSet [-StorageSubSystemFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-DeviceNumbers <String[]>] [-FriendlyName <String>] [-HostType <HostMode>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>]
 [-VirtualDiskNames <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
New-MaskingSet [-AsJob] [-CimSession <CimSession[]>] [-DeviceAccesses <DeviceAccess[]>]
 [-DeviceNumbers <String[]>] [-FriendlyName <String>] [-HostType <HostMode>] [-InitiatorAddresses <String[]>]
 [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] [-VirtualDiskNames <String[]>]
 -StorageSubSystemUniqueId <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
New-MaskingSet [-AsJob] [-DeviceAccesses <DeviceAccess[]>] [-DeviceNumbers <String[]>] [-FriendlyName <String>]
 [-HostType <HostMode>] [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>]
 [-ThrottleLimit <Int32>] [-VirtualDiskNames <String[]>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-MaskingSet [-AsJob] [-CimSession <CimSession[]>] [-DeviceAccesses <DeviceAccess[]>]
 [-DeviceNumbers <String[]>] [-FriendlyName <String>] [-HostType <HostMode>] [-InitiatorAddresses <String[]>]
 [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] [-VirtualDiskNames <String[]>]
 -StorageSubSystemName <String[]>
```

### UNNAMED_PARAMETER_SET_5
```
New-MaskingSet [-CimSession <CimSession[]>]
```

## DESCRIPTION
The **New-MaskingSet** cmdlet creates a new masking set.
Masking sets allow management of groups of TargetPort, VirtualDisk, and InitiatorID objects to manage access to virtual disks, either for individual computers or multiple computers in the case of a Failover Cluster configuration.
Once a masking set is created, adding or removing a virtual disk grants or removes access to all resources in the masking set.
Adding or removing initiator addresses can show or hide the virtual disks in this masking set to hosts.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Create a masking set
```
PS C:\>$StorageSubsystem = Get-StorageSubsystem



PS C:\>$VirtualDisks = Get-VirtualDisk -Name "Virtual01,Virtual02"



PS C:\>$Initiator = Get-InitiatorPort



PS C:\>$Target = Get-TargetPort



PS C:\>New-MaskingSet -StorageSubsystemFriendlyName $StorageSubsystem.FriendlyName -VirtualDiskNames $VirtualDisks.Name -FriendlyName "MyFirstMaskingSet" -InitiatorAddresses $Initiator.NodeAddress -TargetPortAddresses $Target.PortAddress
```

This example collects the necessary information and then creating a new masking set to expose the virtual disks that have the friendly names VirtualDisk01 and VirtualDisk02 to the local machine.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceAccesses
Specifies the way in which initiators can access the virtual disk(s) that are part of this masking set.
You must specify a **DeviceAccesses** value for each virtual disk specified by the **VirtualDiskNames** parameter.
Allowed values are NoAccess, ReadOnly, ReadWrite, and Unknown

```yaml
Type: DeviceAccess[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNumbers
Specifies the device numbers for one or more virtual disks.
Some storage providers do not use device numbers.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name for the new masking set.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: MaskingSetFriendlyName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostType
Specifies the host operating system or other host environmental factors that may influence the behavior that the storage system should have when showing a virtual disk to an initiator.

```yaml
Type: HostMode
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorAddresses
Specifies the initiator addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts a StorageSubsystem object from the pipeline as input.
Enter a StorageSubsystem CIM object, which is returned by the Get-StorageSubSystem cmdlet.

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

### -StorageSubSystemFriendlyName
Specifies the friendly name of the storage subsystem.

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
Specifies the name of the storage subsystem provided by the Storage Management.

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
Specifies the UniqueID of the storage subsystem to use.

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

### -TargetPortAddresses
Specifies one or more target port addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskNames
Specifies one or more virtual disk names to include in the masking set.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/Msft_StorageSubsystem
You can pipe a StorageSubsystem object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
This cmdlet outputs an object representing the newly created masking set.

## NOTES

## RELATED LINKS

[Get-MaskingSet](./Get-MaskingSet.md)

[Get-InitiatorPort](./Get-InitiatorPort.md)

[Get-StorageSubsystem](./Get-StorageSubsystem.md)

[Get-TargetPort](./Get-TargetPort.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Remove-MaskingSet](./Remove-MaskingSet.md)

[Rename-MaskingSet](./Rename-MaskingSet.md)

