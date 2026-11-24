---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Disk.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-disk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Disk
---

# Get-Disk

## SYNOPSIS
Gets one or more disks visible to the operating system.

> [!NOTE]
> This cmdlet returns physical disk objects like basic disks and partitioned drive partitions.  Dynamic disks can span multiple pieces of physical media, so they will not be returned by Get-Disk. For more information, see [Basic and Dynamic Disks](/windows/desktop/FileIO/basic-and-dynamic-disks).

## SYNTAX

### ByNumber (Default)
```
Get-Disk [[-Number] <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByUniqueId
```
Get-Disk [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByName
```
Get-Disk [-FriendlyName <String[]>] [-SerialNumber <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPath
```
Get-Disk [-Path <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPartition
```
Get-Disk [-Partition <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDisk
```
Get-Disk [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSISession
```
Get-Disk [-iSCSISession <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSIConnection
```
Get-Disk [-iSCSIConnection <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-Disk [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageNode
```
Get-Disk [-StorageNode <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageJob
```
Get-Disk [-StorageJob <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-Disk** cmdlet gets one or more Disk objects visible to the operating system, or optionally a filtered list.

## EXAMPLES

### Example 1: Get all disks
```
PS C:\>Get-Disk
```

This example gets all disks visible to the operating system.

### Example 2: Get a disk by disk number
```
PS C:\>Get-Disk -Number 6
```

This example gets disk 6.

### Example 3: Get all USB disks
```
PS C:\>Get-Disk | Where-Object -FilterScript {$_.Bustype -Eq "USB"}
```

This example gets all disks attached via the USB bus by piping the output of Get-Disk to the **Where-Object** cmdlet, and filtering by the USB value of the Bustype property.

### Example 4: Get the iSCSI sessions for all iSCSI disks
```
PS C:\>Get-Disk | Where-Object -FilterScript {$_.BusType -Eq "iSCSI"} |
Get-IscsiSession | Format-Table
```

This example gets all disks attached via the iSCSI bus by piping the output of Get-Disk to the **Where-Object** cmdlet, and filtering by the iSCSI value of the Bustype property.
It then passes the Disk objects in the pipeline to the **Get-IscsiSession** cmdlet, which gets the associated iSCSI sessions, and then pipes the output to the **Format-Table** cmdlet for simplified display.

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

### -FriendlyName
Gets the disk with the specified friendly name.
Enter a friendly name, or use wildcard characters to enter a name pattern.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Number
Specifies the disk number for which to get the associated Disk object.

```yaml
Type: UInt32[]
Parameter Sets: ByNumber
Aliases: DeviceId

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Partition
Accepts a Partition object as input.
The Partition CIM object is exposed by the [Get-Partition](https://technet.microsoft.com/library/85bb3c53-536e-408f-b159-28e91afeb1a1) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPartition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Contains valid path information.

```yaml
Type: String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SerialNumber
Specifies an array of serial numbers associated with disks that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageJob
Specifies a storage job object that is associated with disks that this cmdlet gets.
To obtain a storage job, use the Get-StorageJob cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageJob
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode


```yaml
Type: CimInstance
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Specifies the storage subsystem from which this cmdlet gets disks.
To obtain a **StorageSubsystem** object, use the Get-StorageSubSystem cmdlet.

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
Gets only the disks with the specified IDs.
Type one or more IDs (separated by commas).

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
Accepts a VirtualDisk object as input.
The Virtual Disk CIM object is exposed by the [Get-VirtualDisk](https://technet.microsoft.com/library/0eeba53f-6468-485f-a680-49260b4c83f0) cmdlet.

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

### -iSCSIConnection
Accepts an iSCSIConnection object as input.
The iSCSI Connection CIM object is exposed by the [Get-IscsiConnection](https://technet.microsoft.com/library/e566d297-76ad-48d0-b5af-11674f23b080) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByiSCSIConnection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSISession
Accepts an iSCSISession object as input.
The iSCSI Session CIM object is exposed by the Get-IscsiSession cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByiSCSISession
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiConnection
You can pipe an iSCSIConnection object to the **iSCSIConnection** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_IscsiSession
You can pipe an iSCSISession object to the **iSCSISession** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the **Partition** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the **VirtualDisk** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
This cmdlet outputs one or more objects representing disks.

## NOTES
* The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
* Some objects such as disks might include trailing spaces in their friendly names. If you suspect that an object name could have trailing spaces, you can use a wildcard at the end of the name, for example Disk*, or use the **Match** parameter to instruct Windows PowerShell to include all strings that include the specified characters, instead of only strings that include only the specified characters.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[Clear-Disk](./Clear-Disk.md)

[Get-Partition](./Get-Partition.md)

[Get-StorageJob](./Get-StorageJob.md)

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

[Initialize-Disk](./Initialize-Disk.md)

[Set-Disk](./Set-Disk.md)

[Update-Disk](./Update-Disk.md)
