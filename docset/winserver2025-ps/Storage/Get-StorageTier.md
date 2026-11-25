---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageTier.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagetier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageTier
---

# Get-StorageTier

## SYNOPSIS
Gets storage tiers on Windows Storage subsystems.

## SYNTAX

### ByFriendlyName (Default)
```
Get-StorageTier [[-FriendlyName] <String[]>] [-MediaType <MediaType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageTier [-UniqueId <String[]>] [-MediaType <MediaType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageTier [-MediaType <MediaType[]>] [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStoragePool
```
Get-StorageTier [-MediaType <MediaType[]>] [-StoragePool <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageTier** cmdlet gets storage tiers on Windows Storage subsystems.
Storage tiers are physical disks that are grouped by characteristics, for example, solid-state drives (SSD) and hybrid hard drives (HHD).

## EXAMPLES

### Example 1: Get a storage tier
```
PS C:\>Get-StorageTier -FriendlyName "StoreTier01"
```

This command gets the storage tier named StoreTier01.

### Example 2: Get a storage tier from a storage pool
```
PS C:\> Get-StoragePool -FriendlyName "StorePool01" | Get-StorageTier
```

This command gets the object that contains the storage pool named StorePool01, and then passes the object to the Get-StorageTier cmdlet by using the pipeline operator.
The **Get-StorageTier** cmdlet gets the storage tier from the storage pool object.

### Example 3: Get a storage tier from a virtual disk
```
PS C:\>Get-VirtualDisk -FriendlyName "VDisk01" | Get-StorageTier
```

This command uses the Get-VirtualDisk cmdlet to get the tiered virtual disk named VDisk01.
The command passes the virtual disk to the **Get-StorageTier** cmdlet by using the pipeline operator.
The **Get-StorageTier** cmdlet gets the storage tiers that compose the tiered virtual disk.

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
Specifies an array of friendly names of storage tiers to get.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MediaType
Specifies an array of media types.
The cmdlet gets the storage tiers for the media type that you specify.
The acceptable values for this parameter are:

- SSD
- HDD

```yaml
Type: MediaType[]
Parameter Sets: (All)
Aliases:
Accepted values: Unspecified, HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies a storage pool as a **CIMInstance** object.
The cmdlet gets the storage tiers for the storage pool that you specify.
To obtain a storage pool, use the Get-StoragePool cmdlet.

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
Specifies an array of IDs of storage tiers to get.

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
Specifies a virtual disk as a **CIMInstance** object.
The cmdlet gets the storage tiers for the virtual disk that you specify.
To obtain a virtual disk, use theGet-VirtualDisk cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the *StoragePool* parameter to get the storage tier associated with the **StoragePool** object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an **MSFT_VirtualDisk** object to the *VirtualDisk* parameter to get the storage tier associated with the **VirtualDisk** object.

## OUTPUTS

### MSFT_StorageTier
This cmdlet returns an object that contains details about the storage tier, such as tier friendly name, media type and size.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[New-StorageTier](./New-StorageTier.md)

[Remove-StorageTier](./Remove-StorageTier.md)

[Resize-StorageTier](./Resize-StorageTier.md)

[Set-StorageTier](./Set-StorageTier.md)

