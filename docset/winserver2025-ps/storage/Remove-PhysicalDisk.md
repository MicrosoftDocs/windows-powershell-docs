---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/remove-physicaldisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PhysicalDisk
---

# Remove-PhysicalDisk

## SYNOPSIS
Removes a physical disk from a specified storage pool.

## SYNTAX

### ByStoragePool
```
Remove-PhysicalDisk [-StoragePool] <CimInstance> -PhysicalDisks <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskUniqueId
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskUniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskName
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskFriendlyName
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskFriendlyName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDisk
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> [-VirtualDisk] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolUniqueId
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> -StoragePoolUniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolName
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> -StoragePoolName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolFriendlyName
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> -StoragePoolFriendlyName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-PhysicalDisk** cmdlet removes a physical disk from a specified storage pool.


If sufficient space does not exist in the storage pool to tolerate this removal, then data loss can result (the user is warned about this).
If the user configuration allows, then the user should add a replacement physical disk to the pool prior to removal of the old one.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $PDToRemove = Get-PhysicalDisk -Friendlyname "PhysicalDisk25"
PS C:\> Remove-PhysicalDisk -PhysicalDisks $PDToRemove -StoragePoolFriendlyName "DemoPool"
```

This example removes a specific Physical Disk object from the specified storage pool.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisks
Accepts one or more PhysicalDisk objects as input.
The Physical Disk CIM objects represent the physical disks to be removed from the storage pool.

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

### -StoragePool
Specifies a storage pool as a **CimInstance** object.
The cmdlet removes the physical disk associated with storage pool that you specify.
To obtain a storage pool object, use the Get-StoragePool cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool from which to remove the physical disk.

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
Specifies the name of the storage pool from which to remove the physical disk.

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
Specifies the ID of the storage pool from which to remove the physical disk.

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

### -VirtualDisk
Specifies a virtual disk as a **CimInstance** object.
The cmdlet removes the physical disk associated with virtual disk that you specify.
To obtain a virtual disk object, use the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDiskFriendlyName
Specifies the friendly name of the virtual disk from which to remove the physical disk.

```yaml
Type: String
Parameter Sets: ByVirtualDiskFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskName
Specifies the name of the virtual disk from which to remove the physical disk.

```yaml
Type: String
Parameter Sets: ByVirtualDiskName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskUniqueId
Specifies the ID of the virtual disk from which to remove the physical disk.

```yaml
Type: String
Parameter Sets: ByVirtualDiskUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisks

You can use the pipeline operator to pass an array of MSFT_PhysicalDisk objects to the *PhysicalDisks* parameter

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool

You can use the pipeline operator to pass an MSFT_StoragePool object to the *StoragePool* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk

You can use the pipeline operator to pass an MSFT_VirtualDisk object to the *VirtualDisk* parameter.

## OUTPUTS

### None

By default, this cmdlet doesn't return any output.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Add-PhysicalDisk](./Add-PhysicalDisk.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)
