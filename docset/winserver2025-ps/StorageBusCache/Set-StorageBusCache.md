---
external help file: StorageBusCache-help.xml
Module Name: StorageBusCache
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagebuscache/set-storagebuscache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageBusCache
---

# Set-StorageBusCache

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Set-StorageBusCache [[-CacheMetadataReserveBytes] <UInt64>] [[-CacheModeHDD] <CacheModeSet>]
 [[-CacheModeSSD] <CacheModeSet>] [[-CachePageSizeKBytes] <UInt32>] [[-SharedCachePercent] <UInt32>]
 [[-ProvisionMode] <ProvisionMode>] [<CommonParameters>]
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
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheModeHDD
{{ Fill CacheModeHDD Description }}

```yaml
Type: Microsoft.Windows.Storage.StorageBusCache.CacheModeSet
Parameter Sets: (All)
Aliases:
Accepted values: ReadOnly, ReadWrite, WriteOnly

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheModeSSD
{{ Fill CacheModeSSD Description }}

```yaml
Type: Microsoft.Windows.Storage.StorageBusCache.CacheModeSet
Parameter Sets: (All)
Aliases:
Accepted values: ReadOnly, ReadWrite, WriteOnly

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CachePageSizeKBytes
{{ Fill CachePageSizeKBytes Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:
Accepted values: 8, 16, 32, 64

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisionMode
{{ Fill ProvisionMode Description }}

```yaml
Type: Microsoft.Windows.Storage.StorageBusCache.ProvisionMode
Parameter Sets: (All)
Aliases:
Accepted values: Shared, Cache

Required: False
Position: 5
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
Position: 4
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
