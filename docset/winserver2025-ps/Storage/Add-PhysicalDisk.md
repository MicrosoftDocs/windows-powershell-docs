---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/add-physicaldisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PhysicalDisk
---

# Add-PhysicalDisk

## SYNOPSIS
Adds a physical disk to the specified storage pool or manually assigns a physical disk to a specific virtual disk.

## SYNTAX

### ByStoragePool
```
Add-PhysicalDisk [-StoragePool] <CimInstance> -PhysicalDisks <CimInstance[]> [-Usage <Usage>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskUniqueId
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskUniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDiskFriendlyName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> -VirtualDiskFriendlyName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualDisk
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-VirtualDisk] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolUniqueId
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-Usage <Usage>] -StoragePoolUniqueId <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-Usage <Usage>] -StoragePoolName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStoragePoolFriendlyName
```
Add-PhysicalDisk -PhysicalDisks <CimInstance[]> [-Usage <Usage>] -StoragePoolFriendlyName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-PhysicalDisk** cmdlet adds a physical disk to the specified storage pool.
The cmdlet can also assign a ManualSelect physical disk already in the storage pool to a specific virtual disk.

## EXAMPLES

### Example 1: Adding a physical disk by storage pool friendly name
```
PS C:\> $PDToAdd = Get-PhysicalDisk -FriendlyName PhysicalDisk5
PS C:\> Add-PhysicalDisk -PhysicalDisks $PDToAdd -StoragePoolFriendlyName CompanyData
```

This example gets the PhysicalDisk object for the physical disk named PhysicalDisk5 and assigns it to the $PDToAdd variable.
It then adds the PhysicalDisk object to the storage pool named CompanyData.

### Example 2: Adding all available physical disks
```
PS C:\> $PDToAdd = Get-PhysicalDisk -CanPool $True
PS C:\> Add-PhysicalDisk -StoragePoolFriendlyName "Demo Pool" -PhysicalDisks $PDToAdd
```

This example gets all PhysicalDisk objects that can be added to a storage pool and assigns them to the $PDToAdd variable.
It then adds the available physical disks to the storage pool named Demo Pool.

### Example 3: Piping a storage pool to Add-PhysicalDisk
```
PS C:\> Get-StoragePool -IsPrimordial $False | Add-PhysicalDisk -PhysicalDisks (Get-PhysicalDisk -CanPool $True)
```

This example gets all storage pools (except primordial pools) and pipes the output to the Add-PhysicalDisk cmdlet (this will not work if you created more than one storage pool).
This example then uses the Get-Physical Disk cmdlet inside of parentheses to specify all available physical disks without using variables.

### Example 4: Manually assigning physical disks to a virtual disk
```
PS C:\> Add-PhysicalDisk -VirtualDiskFriendlyName UserData -PhysicalDisks (Get-PhysicalDisk -FriendlyName PhysicalDisk3, PhysicalDisk4)
```

This example gets two physical disks that have already been added to the storage pool and designated as ManualSelect disks, PhysicalDisk3 and PhysicalDisk4, and assigns them to the virtual disk UserData.

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
Specifies the physical disk objects to add to the storage pool.
Enter one or more PhysicalDisk CIM objects.

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
Specifies the storage pool object to which you want to add the physical disk(s).
Enter a StoragePool CIM object.

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
Specifies the friendly name of the storage pool to which to add the physical disk.

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
Specifies the name of the storage pool, provided by the Storage Management Provider, to which to add the physical disk.

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
Specifies the ID of the storage pool to which to add the physical disk.

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

### -Usage
Specifies the allocation method (usage) for the disk.
Valid values are AutoSelect, HotSpare, Journal, ManualSelect, Retired, and Unknown.

```yaml
Type: Usage
Parameter Sets: ByStoragePool, ByStoragePoolUniqueId, ByStoragePoolName, ByStoragePoolFriendlyName
Aliases:
Accepted values: AutoSelect, ManualSelect, HotSpare, Retired, Journal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
Specifies the virtual disk object to which to exclusively assign the physical disk(s).
Enter one or more VirtualDisk CIM objects.

To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

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
Specifies the friendly name of the virtual disk to which to exclusively assign the physical disks.

To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

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
Specifies the ID of the virtual disk to which to exclusively assign the physical disks.

To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe an MSFT_StoragePool object to the *StoragePool* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the *VirtualDisk* parameter.

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=809329)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Remove-PhysicalDisk](./Remove-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

