---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageSubSystem.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-maskingset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-MaskingSet
---

# New-MaskingSet

## SYNOPSIS
Creates a new masking set.

## SYNTAX

### ByFriendlyName (Default)
```
New-MaskingSet [-StorageSubSystemFriendlyName] <String[]> [-FriendlyName <String>]
 [-VirtualDiskNames <String[]>] [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>]
 [-DeviceNumbers <String[]>] [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-MaskingSet -StorageSubSystemUniqueId <String[]> [-FriendlyName <String>] [-VirtualDiskNames <String[]>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-DeviceNumbers <String[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-MaskingSet -StorageSubSystemName <String[]> [-FriendlyName <String>] [-VirtualDiskNames <String[]>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-DeviceNumbers <String[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-MaskingSet -InputObject <CimInstance[]> [-FriendlyName <String>] [-VirtualDiskNames <String[]>]
 [-InitiatorAddresses <String[]>] [-TargetPortAddresses <String[]>] [-DeviceNumbers <String[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-HostType <HostMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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
PS C:\> $StorageSubsystem = Get-StorageSubsystem
PS C:\> $VirtualDisks = Get-VirtualDisk -Name "Virtual01,Virtual02"
PS C:\> $Initiator = Get-InitiatorPort
PS C:\> $Target = Get-TargetPort
PS C:\> New-MaskingSet -StorageSubsystemFriendlyName $StorageSubsystem.FriendlyName -VirtualDiskNames $VirtualDisks.Name -FriendlyName "MyFirstMaskingSet" -InitiatorAddresses $Initiator.NodeAddress -TargetPortAddresses $Target.PortAddress
```

This example collects the necessary information and then creating a new masking set to expose the virtual disks that have the friendly names VirtualDisk01 and VirtualDisk02 to the local machine.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DeviceAccesses
Specifies the way in which initiators can access the virtual disk(s) that are part of this masking set.
You must specify a **DeviceAccesses** value for each virtual disk specified by the *VirtualDiskNames* parameter.
Allowed values are NoAccess, ReadOnly, ReadWrite, and Unknown.

```yaml
Type: DeviceAccess[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, ReadWrite, ReadOnly, NoAccess

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Other, Standard, Solaris, HPUX, OpenVMS, Tru64, Netware, Sequent, AIX, DGUX, Dynix, Irix, CiscoISCSIStorageRouter, Linux, MicrosoftWindows, OS400, TRESPASS, HIUX, VMwareESXi, MicrosoftWindowsServer2008, MicrosoftWindowsServer2003

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

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

### -StorageSubSystemFriendlyName
Specifies the friendly name of the storage subsystem.

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

### -StorageSubSystemName
Specifies the name of the storage subsystem provided by the Storage Management.

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

### -StorageSubSystemUniqueId
Specifies the UniqueID of the storage subsystem to use.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
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

### -VirtualDiskNames
Specifies one or more virtual disk names to include in the masking set.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/Msft_StorageSubsystem
You can pipe a StorageSubsystem object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
This cmdlet outputs an object representing the newly created masking set.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-MaskingSet](./Get-MaskingSet.md)

[Get-InitiatorPort](./Get-InitiatorPort.md)

[Get-TargetPort](./Get-TargetPort.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Remove-MaskingSet](./Remove-MaskingSet.md)

[Rename-MaskingSet](./Rename-MaskingSet.md)

