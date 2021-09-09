---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Enable-StorageDataCollection

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByPhysicalDisk
```
Enable-StorageDataCollection -PhysicalDisk <CimInstance> -StorageDataCollectionType <StorageDataCollectionType>
 [<CommonParameters>]
```

### ByDeviceGuid
```
Enable-StorageDataCollection -DeviceGuid <String> -StorageDataCollectionType <StorageDataCollectionType>
 [<CommonParameters>]
```

### ByDeviceNumber
```
Enable-StorageDataCollection -DeviceNumber <String> -StorageDataCollectionType <StorageDataCollectionType>
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
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
{{ Fill DeviceNumber Description }}

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
{{ Fill PhysicalDisk Description }}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
