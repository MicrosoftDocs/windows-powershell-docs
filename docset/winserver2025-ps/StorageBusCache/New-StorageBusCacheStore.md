---
external help file: StorageBusCache-help.xml
Module Name: StorageBusCache
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagebuscache/new-storagebuscachestore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StorageBusCacheStore
---

# New-StorageBusCacheStore

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByGuid
```
New-StorageBusCacheStore -Guid <String> [-CachePageSizeKBytes <UInt32>] [-CacheMetadataReserveBytes <UInt64>]
 [-SharedCachePercent <UInt32>] [<CommonParameters>]
```

### ByNumber
```
New-StorageBusCacheStore -Number <UInt32> [-CachePageSizeKBytes <UInt32>] [-CacheMetadataReserveBytes <UInt64>]
 [-SharedCachePercent <UInt32>] [<CommonParameters>]
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

### -CacheMetadataReserveBytes
{{ Fill CacheMetadataReserveBytes Description }}

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases: $ReserveCapacity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CachePageSizeKBytes
{{ Fill CachePageSizeKBytes Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: PageSize
Accepted values: 8, 16, 32, 64

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid
{{ Fill Guid Description }}

```yaml
Type: System.String
Parameter Sets: ByGuid
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Number
{{ Fill Number Description }}

```yaml
Type: System.UInt32
Parameter Sets: ByNumber
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedCachePercent
{{ Fill SharedCachePercent Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
