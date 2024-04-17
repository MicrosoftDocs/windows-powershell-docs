---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagefaultdomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageFaultDomain
---

# Get-StorageFaultDomain

## SYNOPSIS
Gets a Storage fault domain object.

## SYNTAX

### EnumerateFaultDomains (Default)
```
Get-StorageFaultDomain [-Type <StorageFaultDomainType>] [-PhysicalLocation <String>] [-CimSession <CimSession>]
 [<CommonParameters>]
```

### ByStorageFaultDomain
```
Get-StorageFaultDomain [-Type <StorageFaultDomainType>] [-PhysicalLocation <String>]
 -StorageFaultDomain <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageSubsystem
```
Get-StorageFaultDomain [-Type <StorageFaultDomainType>] [-PhysicalLocation <String>]
 -StorageSubsystem <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageFaultDomain** cmdlet gets a Storage fault domain object.

## EXAMPLES

### Example 1: Find a rack by its serial number
```
PS C:\>$Rack = Get-StorageFaultDomain -Type Rack | Where-Object {$_.SerialNumber -eq "xyzz"}
```

The first command gets the Rack domain type fault domains and uses the pipeline to pass them to Where-Object, which finds the Rack whose serial number is xyzz.
The Rack is stored in the $Rack variable.

## PARAMETERS

### -CimSession


```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalLocation
Specifies the physical location of the hardware.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFaultDomain
Specifies the objects in the hierarchy that are above or below the fault domain.

```yaml
Type: CimInstance
Parameter Sets: ByStorageFaultDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubsystem
Specifies the storage subsystem object in which to retrieve storage jobs.
Enter a StorageSubsystem CIM object.
The StorageSubsystem CIM object is exposed by the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubsystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type
Specifies the Storage fault domain type:

- PhysicalDisk
- Enclosure
- StorageScaleUnit
- Rack
- Chassis

```yaml
Type: StorageFaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack, StorageSite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_PhysicalDisk, MSFT_StorageEnclosure, MSFT_StorageScaleUnit, MSFT_StorageRack, MSFT_StorageChassis

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

