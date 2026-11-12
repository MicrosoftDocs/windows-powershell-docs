---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/set-deliveryoptimizationstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DeliveryOptimizationStatus
---

# Set-DeliveryOptimizationStatus

## SYNOPSIS

Sets the expiration time or pinning status of Delivery Optimization cached files.

## SYNTAX

```
Set-DeliveryOptimizationStatus [[-FileId] <String>] [[-Pin] <Boolean>] [[-ExpireOn] <DateTime>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-DeliveryOptimizationStatus` cmdlet changes the expiration time or pinning status of
files in the Delivery Optimization cache.

Use **ExpireOn** to extend the expiration of a specific file, or omit **FileId** to apply the
expiration to all files. For downloads in progress, the expiration is applied after completion.

Use **Pin** with **FileId** to pin or unpin a specific file. Pinned files are retained until their
expiration and excluded from cache quota calculations. Unpinned files are subject to normal
cache management.

Specify at least one of **Pin** or **ExpireOn**. Pinning or unpinning requires **FileId**.

## EXAMPLES

### Example 1: Extend expiration for cached files

```powershell
Set-DeliveryOptimizationStatus -ExpireOn (Get-Date).AddDays(7)
```

This command sets the cache expiration to seven days from now for all files.

### Example 2: Pin a specific file and set its expiration

```powershell
$fileId = '0123456789abcdef0123456789abcdef'
Set-DeliveryOptimizationStatus -FileId $fileId -Pin $true -ExpireOn (Get-Date).AddDays(7)
```

This command pins the specified file and sets its expiration to seven days from now.
Replace the example ID with a **FileId** returned by `Get-DeliveryOptimizationStatus`.

### Example 3: Unpin a cached file

```powershell
Set-DeliveryOptimizationStatus -FileId '0123456789abcdef0123456789abcdef' -Pin $false
```

This command unpins the specified file, making it subject to normal cache management.

## PARAMETERS

### -ExpireOn

Specifies the cache expiration date and time. Set a future expiration less than one year from
the current date and time. If you omit **FileId**, the expiration applies to all files.
For files still downloading, the expiration takes effect when the download completes.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileId

Specifies the ID of the file to update. Use `Get-DeliveryOptimizationStatus` to find file IDs.
This parameter is required when you specify **Pin**. If you specify only **ExpireOn** and omit
this parameter, the expiration applies to all files.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pin

Specifies whether to pin the file. Set this parameter to `$true` to pin or `$false` to unpin.
You must also specify **FileId**. Pinning fails if the file isn't eligible for peering.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You can't pipe objects to this cmdlet.

## OUTPUTS

### None

This cmdlet doesn't return objects. It displays update status messages in the console.

## NOTES

Run this cmdlet from an elevated PowerShell session. Use `Get-DeliveryOptimizationStatus` to
check the resulting **ExpireOn** and **IsPinned** properties.

## RELATED LINKS

[Get-DeliveryOptimizationStatus](Get-DeliveryOptimizationStatus.md)

[Delete-DeliveryOptimizationCache](Delete-DeliveryOptimizationCache.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
