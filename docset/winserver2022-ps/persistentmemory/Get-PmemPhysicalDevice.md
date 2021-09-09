---
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
online version:
schema: 2.0.0
---

# Get-PmemPhysicalDevice

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### AllDevices (Default)
```
Get-PmemPhysicalDevice [<CommonParameters>]
```

### ByDeviceId
```
Get-PmemPhysicalDevice [[-DeviceId] <String[]>] [<CommonParameters>]
```

### ByPmemDisk
```
Get-PmemPhysicalDevice [-LogicalDisk <PmemDisk>] [<CommonParameters>]
```

### ByDiskNumber
```
Get-PmemPhysicalDevice [-DiskNumber <UInt32>] [<CommonParameters>]
```

### ByInputObject
```
Get-PmemPhysicalDevice [-InputObject <CimInstance>] [<CommonParameters>]
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

### -DeviceId
{{ Fill DeviceId Description }}

```yaml
Type: String[]
Parameter Sets: ByDeviceId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
{{ Fill DiskNumber Description }}

```yaml
Type: UInt32
Parameter Sets: ByDiskNumber
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogicalDisk
{{ Fill LogicalDisk Description }}

```yaml
Type: PmemDisk
Parameter Sets: ByPmemDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Storage.PersistentMemory.Management.PmemDisk

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Storage.PersistentMemory.Management.PmemPhysicalDevice

## NOTES

## RELATED LINKS
