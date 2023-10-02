---
external help file: StorSpaces2_Cmdlets.xml
Module Name: StorageSpaces
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/storagespaces/get-spacespoolphysicaldiskhwcounter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SpacesPoolPhysicalDiskHWCounter
---

# Get-SpacesPoolPhysicalDiskHWCounter

## SYNOPSIS
Collects hardware-based reliability counters for all physical disks in a given Storage Spaces pool.

## SYNTAX

```
Get-SpacesPoolPhysicalDiskHWCounter [-StoragePoolFriendlyName] <String>
```

## DESCRIPTION
The Get-SpacesPoolPhysicalDiskHWCounter cmdlet gets objects that represent the reliability counters for all physical disks in a given Storage Spaces pool.
The information included is dependent on the disk, and can include such information as the number of hours disk has been powered on, the temperature, errors, and maximum latencies.

## EXAMPLES

### Example 1 - Get the hardware counters for a Storage Spaces pool
```
PS C:\>Get-SpacesPoolPhysicalDiskHWCounter -StoragePoolFriendlyName Internal
PhysicalDiskFriendlyName  : 3TB Sata 3
PhysicalDiskUniqueID      : SCSI\Disk&Ven_WDC&Prod_WD30EZRX-00MMMB0\5&34a7a490&0&000000:SpaceDock
CurrentTemperatureCelsius : 32
PowerOnHours              : 253
ReadErrorsTotal           : 0
WriteErrorsTotal          :
ReadLatencyMax            : 531
WriteLatencyMax           : 30



PhysicalDiskFriendlyName  : Hitachi HDS723030ALA640 ATA Device
PhysicalDiskUniqueID      : IDE\DiskHitachi_HDS723030ALA640_________________MKAOA340\5&3c1a333&0&1.0.0:SpaceDock
CurrentTemperatureCelsius : 34
PowerOnHours              : 9187
ReadErrorsTotal           : 0
WriteErrorsTotal          :
ReadLatencyMax            : 254
WriteLatencyMax           : 4

PhysicalDiskFriendlyName  : WDC WD30EZRX-00MMMB0
PhysicalDiskUniqueID      : SCSI\Disk&Ven_WDC&Prod_WD30EZRX-00MMMB0\4&14267af2&0&010000:SpaceDock
CurrentTemperatureCelsius : 28
PowerOnHours              : 901
ReadErrorsTotal           : 0
WriteErrorsTotal          :
ReadLatencyMax            : 440
WriteLatencyMax           : 0



PhysicalDiskFriendlyName  : WDC WD20EARS-00MVWB0
PhysicalDiskUniqueID      : SCSI\Disk&Ven_WDC&Prod_WD20EARS-00MVWB0\4&14267af2&0&030000:SpaceDock
CurrentTemperatureCelsius : 27
PowerOnHours              : 8382
ReadErrorsTotal           : 0
WriteErrorsTotal          :
ReadLatencyMax            : 454
WriteLatencyMax           : 26
```

## PARAMETERS

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### System.Object
This cmdlet returns objects that represent the reliability counters for all physical disks in a given Storage Spaces pool.

## NOTES

## RELATED LINKS

