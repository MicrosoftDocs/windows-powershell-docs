---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StoragePool.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-virtualdisksupportedsize?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VirtualDiskSupportedSize
---

# Get-VirtualDiskSupportedSize

## SYNOPSIS
Returns all sizes supported by a storage pool for virtual disk creation based on the specified resiliency setting name.

## SYNTAX

### ByFriendlyName (Default)
```
Get-VirtualDiskSupportedSize [-StoragePoolFriendlyName] <String[]> [-ResiliencySettingName <String>]
 [-FaultDomainAwareness <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByUniqueId
```
Get-VirtualDiskSupportedSize -StoragePoolUniqueId <String[]> [-ResiliencySettingName <String>]
 [-FaultDomainAwareness <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByName
```
Get-VirtualDiskSupportedSize -StoragePoolName <String[]> [-ResiliencySettingName <String>]
 [-FaultDomainAwareness <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-VirtualDiskSupportedSize -InputObject <CimInstance[]> [-ResiliencySettingName <String>]
 [-FaultDomainAwareness <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VirtualDiskSupportedSize** cmdlet returns all sizes supported by a storage pool for virtual disk creation based on the specified resiliency setting name.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-VirtualDiskSupportedSize -ResiliencySettingsName Mirror
```

This example lists the minimum and maximum supported sizes for virtual disk creation using the specified resiliency settings name.

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

### -FaultDomainAwareness
Specifies the desired level of fault tolerance.
The acceptable values for this parameter are:

- PhysicalDisk
- StorageScaleUnit
- StorageChassis
- StorageEnclosure
- StorageRack

For example, specify StorageScaleUnit if data copies should be stored on separate nodes of a Storage Spaces Direct cluster.
This cmdlet refers to nodes of a Storage Spaces Direct cluster as storage scale units because you can expand the scale of the cluster by adding more nodes.

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

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

### -ResiliencySettingName
Specifies the name of the desired resiliency setting, for example **Simple**, **Mirror**, or **Parity**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies an array of friendly names of storage pools.
The cmdlet returns all sizes supported by the storage pools that you specify.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases: FriendlyName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoragePoolName
Specifies an array of names of storage pools.
The cmdlet returns all sizes supported by the storage pools that you specify.

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

### -StoragePoolUniqueId
Specifies an array of unique IDs of storage pools, as strings.
The cmdlet returns all sizes supported by the storage pools that you specify.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StoragePoolId, UniqueId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the **InputObject** parameter.

## OUTPUTS

### System.Management.Automation.PSCustomObject
This cmdlet returns an object that lists the minimum and maximum size for creating a virtual disk in the specified pool with the specified resiliency setting.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-ResiliencySetting](./Get-ResiliencySetting.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Get-StorageTierSupportedSize](./Get-StorageTierSupportedSize.md)

[Set-ResiliencySetting](./Set-ResiliencySetting.md)

