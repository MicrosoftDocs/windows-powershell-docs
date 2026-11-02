---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/delete-deliveryoptimizationcache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Delete-DeliveryOptimizationCache
---

# Delete-DeliveryOptimizationCache

## SYNOPSIS

Deletes files from the Delivery Optimization cache.

## SYNTAX

```
Delete-DeliveryOptimizationCache [[-FileId] <String>] [-IncludePinnedFiles] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION

The `Delete-DeliveryOptimizationCache` cmdlet deletes cached Delivery Optimization files and
their associated persisted data. By default, pinned files aren't deleted.

Use the **FileId** parameter to delete a specific file. If you omit **FileId**, the cmdlet
deletes all eligible files in the cache. Use **IncludePinnedFiles** to also delete pinned files.

The cmdlet prompts before deleting files unless you specify **Force**. Deletion can't be undone.

## EXAMPLES

### Example 1: Clear the cache without deleting pinned files

```powershell
Delete-DeliveryOptimizationCache
```

This command prompts for confirmation, then deletes unpinned files from the cache.

### Example 2: Delete a specific cached file

```powershell
Delete-DeliveryOptimizationCache -FileId '0123456789abcdef0123456789abcdef'
```

This command prompts before deleting the specified file. Replace the example ID with a
**FileId** returned by `Get-DeliveryOptimizationStatus`.

### Example 3: Delete all cached files, including pinned files

```powershell
Delete-DeliveryOptimizationCache -IncludePinnedFiles -Force
```

This command deletes both pinned and unpinned files without prompting.

## PARAMETERS

### -FileId

Specifies the ID of the cached file to delete. Use `Get-DeliveryOptimizationStatus` to find
file IDs. If you omit this parameter, the cmdlet deletes all eligible cached files.

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

### -Force

Deletes files without prompting for confirmation. This parameter doesn't allow deletion of
pinned files unless you also specify **IncludePinnedFiles**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludePinnedFiles

Includes pinned files in the deletion. By default, the cmdlet preserves pinned files.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
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

This cmdlet doesn't return objects. It displays deletion status messages in the console.

## NOTES

Run this cmdlet from an elevated PowerShell session.

## RELATED LINKS

[Get-DeliveryOptimizationStatus](Get-DeliveryOptimizationStatus.md)

[Set-DeliveryOptimizationStatus](Set-DeliveryOptimizationStatus.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
