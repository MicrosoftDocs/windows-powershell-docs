---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-virtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VirtualDisk
---

# Set-VirtualDisk

## SYNOPSIS
Modifies the attributes of an existing virtual disk.

## SYNTAX

### ByUniqueId (Default)
```
Set-VirtualDisk [-NewFriendlyName <String>] [-Usage <Usage>] [-OtherUsageDescription <String>]
 -UniqueId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### ByUniqueIdAttributes
```
Set-VirtualDisk -UniqueId <String> [-IsManualAttach <Boolean>] [-StorageNodeName <String>] [-Access <Access>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameAttributes
```
Set-VirtualDisk [-FriendlyName] <String> [-IsManualAttach <Boolean>] [-StorageNodeName <String>]
 [-Access <Access>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameAttributes
```
Set-VirtualDisk -Name <String> [-IsManualAttach <Boolean>] [-StorageNodeName <String>] [-Access <Access>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VirtualDisk** cmdlet modifies the attributes of an existing virtual disk.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-VirtualDisk -FriendlyName VirtualDisk1 -NewFriendlyName "Storage For Contoso"
```

This example changes the friendly name of a virtual disk.

### EXAMPLE 2
```
PS C:\>Set-VirtualDisk -FriendlyName "Storage For Contoso" -IsManualAttach $False
```

This example attaches a virtual disk that is currently set to manual-attach.

## PARAMETERS

### -Access
Manages access permissions to the VirtualDisk object.

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

### -FriendlyName
Specifies a friendly name for a disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String
Parameter Sets: ByFriendlyName, ByFriendlyNameAttributes
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectAttributes, ByObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsManualAttach
Specifies that the object is set as manual-attach.

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

### -Name
Specifies the name of the virtual disk to modify.

```yaml
Type: String
Parameter Sets: ByName, ByNameAttributes
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies the new name of the virtual disk.

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

### -OtherUsageDescription
Specifies the usage of this object.

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

### -StorageNodeName
Specifies the name of the computer on which to run the cmdlet.

Use this parameter only when you run the cmdlet from a management node to modify a virtual disk on a remote cluster subsystem for the purpose of setting the manual-attach attribute of the virtual disk.
Specify the **IsManualAttach** parameter to set the manual-attach attribute of the virtual disk.

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
Specifies the unique ID of the virtual disk to modify.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByUniqueIdAttributes
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Specifies the intended usage.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an MSFT_VirtualDisk object to the *InputObject* parameter.

## OUTPUTS

### None

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)

