---
author: Kateyanne
description: 
external help file: StorageCmdlets.cdxml-help.xml
manager: jasgro
Module Name: Storage
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storage/remove-physicaldisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PhysicalDisk
---

# Remove-PhysicalDisk

## SYNOPSIS
Removes a physical disk from a specified storage pool.

## SYNTAX

### ByStoragePool
```
Remove-PhysicalDisk [[-StoragePool] <CimInstance>] [-StoragePoolFriendlyName <String>]
 [-StoragePoolName <String>] [-StoragePoolUniqueId <String>] -PhysicalDisks <CimInstance[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDisk
```
Remove-PhysicalDisk -PhysicalDisks <CimInstance[]> [[-VirtualDisk] <CimInstance>]
 [-VirtualDiskFriendlyName <String>] [-VirtualDiskName <String>] [-VirtualDiskUniqueId <String>]
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

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool.
The cmdlet removes the physical disk associated with storage pool that you specify.

```yaml
Type: String
Parameter Sets: ByStoragePool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolName
Specifies the name of the storage pool provided by the Storage Management Provider.
The cmdlet removes the physical disk associated with storage pool that you specify.

```yaml
Type: String
Parameter Sets: ByStoragePool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolUniqueId
Specifies an ID used to uniquely identify a storage pool in the system.
The ID persists through reboots.

```yaml
Type: String
Parameter Sets: ByStoragePool
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

### -VirtualDisk
Specifies a virtual disk as a **CimInstance** object.
The cmdlet removes the physical disk associated with virtual disk that you specify.
To obtain a virtual disk object, use the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDiskFriendlyName
Specifies the friendly name of a virtual disk.
The cmdlet removes the physical disk associated with virtual disk that you specify.

```yaml
Type: String
Parameter Sets: ByVirtualDisk
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskName
Specifies the name of a virtual disk.
The cmdlet removes the physical disk associated with virtual disk that you specify.

```yaml
Type: String
Parameter Sets: ByVirtualDisk
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskUniqueId
Specifies the unique ID of a virtual disk.
The cmdlet removes the physical disk associated with virtual disk that you specify.

```yaml
Type: String
Parameter Sets: ByVirtualDisk
Aliases: 

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisks
You can use the pipeline operator to pass an array of MSFT_PhysicalDisk objects to the **PhysicalDisks** parameter

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the **StoragePool** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an MSFT_VirtualDisk object to the **VirtualDisk** parameter.

## OUTPUTS

###  
This cmdlet does not generate output.

## NOTES

## RELATED LINKS

[Add-PhysicalDisk](./Add-PhysicalDisk.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

