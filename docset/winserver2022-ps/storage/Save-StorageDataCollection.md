---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 08/30/2021
online version: https://docs.microsoft.com/powershell/module/storage/save-storagedatacollection?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-StorageDataCollection
---

# Save-StorageDataCollection

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByPhysicalDisk
```
Save-StorageDataCollection -PhysicalDisk <CimInstance> -StorageDataCollectionType <StorageDataCollectionType>
 [<CommonParameters>]
```

### ByDeviceGuid
```
Save-StorageDataCollection -DeviceGuid <String> -StorageDataCollectionType <StorageDataCollectionType>
 [<CommonParameters>]
```

### ByDeviceNumber
```
Save-StorageDataCollection -DeviceNumber <String> -StorageDataCollectionType <StorageDataCollectionType>
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -DeviceGuid
{{ Fill DeviceGuid Description }}

```yaml
Type: String
Parameter Sets: ByDeviceGuid
Aliases: DeviceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNumber
Specifies the device number.

```yaml
Type: String
Parameter Sets: ByDeviceNumber
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
Specifies a physical disk as a **CimInstance** object.
To obtain a physical disk object, use the **Get-PhysicalDisk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageDataCollectionType
{{ Fill StorageDataCollectionType Description }}

```yaml
Type: StorageDataCollectionType
Parameter Sets: (All)
Aliases:
Accepted values: StorageIoDistribution

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
