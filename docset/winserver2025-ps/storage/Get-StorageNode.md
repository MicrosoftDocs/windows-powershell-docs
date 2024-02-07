---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageNode.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagenode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageNode
---

# Get-StorageNode

## SYNOPSIS
Gets storage nodes.

## SYNTAX

### ByName (Default)
```
Get-StorageNode [-Name <String[]>] [-OperationalStatus <OperationalStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageNode [-UniqueId <String[]>] [-OperationalStatus <OperationalStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectId
```
Get-StorageNode [-ObjectId <String[]>] [-OperationalStatus <OperationalStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVolume
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-Volume <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-VirtualDisk <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-PhysicalDisk <CimInstance>] [-PhysicallyConnected]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStoragePool
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-StoragePool <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageEnclosure
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-StorageEnclosure <CimInstance>]
 [-PhysicallyConnected] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-StorageSubSystem <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDisk
```
Get-StorageNode [-OperationalStatus <OperationalStatus[]>] [-Disk <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageNode** cmdlet gets objects that represent storage nodes and their operational statuses.
Use this cmdlet to get storage nodes to pass to the **Get-PhysicalDisk** cmdlet or the **Get-VirtualDisk** cmdlet to get the physical or virtual disks connected to storage nodes.
Use the current cmdlet with the **Get-StoragePool** cmdlet to get the storage pools that storage nodes own.

## EXAMPLES

### Example 1: Get a storage node
```
PS C:\>Get-StorageNode -Name "StorageNode21"
```

This command gets a storage node named StorageNode21.

### Example 2: Get the operational statuses for all physical disks
```
PS C:\>Get-PhysicalDisk | Get-StorageNode
```

This command uses the **Get-PhysicalDisk** cmdlet to obtain all the physical disks, and then passes them to the current cmdlet by using the pipeline operator.
The cmdlet gets the storage nodes and operational statuses for the physical disks.

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

### -Disk
Specifies a disk for which this cmdlet gets storage notes.
To obtain a **Disk** object, use the **Get-Disk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names.
The cmdlet gets the storage nodes that you specify by name.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Specifies an array of object IDs, as strings.

```yaml
Type: String[]
Parameter Sets: ByObjectId
Aliases: StorageNodeObjectId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationalStatus
Specifies an array of **OperationStatus** objects.
The cmdlet gets storage nodes that match the operational statuses that you specify.
The acceptable values for this parameter are:

- Dormant
- Down
- LowerLayerDown
- NotPresent
- Testing
- Unknown
- Up

```yaml
Type: OperationalStatus[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Up, Down, Joining, Paused

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
Specifies a physical disk as a **CimInstance** object.
The cmdlet gets the storage nodes that correspond to the disk that you specify.
To obtain a physical disk object, use the **Get-PhysicalDisk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicallyConnected
Indicates that this cmdlet gets the storage nodes that are physically connected to a device.

```yaml
Type: SwitchParameter
Parameter Sets: ByPhysicalDisk, ByStorageEnclosure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageEnclosure
Specifies a storage enclosure that is associated with the storage nodes to get.
To obtain a **StorageEnclosure** object, use the Get-StorageEnclosure cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageEnclosure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePool
Specifies a storage pool as a **CimInstance** object.
The cmdlet gets storage node associated with storage pool that you specify.
To obtain a storage pool object, use the **Get-StoragePool** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Specifies a storage subsystem as a **CimInstance** object.
The cmdlet gets the storage nodes that belong to the subsystem that you specify.
To obtain a storage subsystem object, use the **Get-StorageSubSystem** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies an array of unique IDs, as strings.
The cmdlet gets the storage nodes that have the IDs that you specify.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Specifies a virtual disk as a **CimInstance** object.
The cmdlet gets the storage nodes that correspond to the disk that you specify.
To obtain a virtual disk object, use the **Get-VirtualDisk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Volume
Specifies a volume.
The cmdlet gets the storage nodes that correspond to the volume that you specify.
To obtain a **Volume** object, use the Get-Volume cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVolume
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_StorageNode[]
This cmdlet outputs an array of objects that represent storage nodes and their operational statuses.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Disk](./Get-Disk.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-StorageEnclosure](./Get-StorageEnclosure.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Get-Volume](./Get-Volume.md)

