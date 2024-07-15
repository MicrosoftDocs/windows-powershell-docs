---
external help file: Microsoft.Windows.DeliveryOptimization.AdminCommands.dll-Help.xml
Module Name: DeliveryOptimization
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-deliveryoptimizationlog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DeliveryOptimizationLog
---

# Get-DeliveryOptimizationLog

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Get-DeliveryOptimizationLog [-LevelFilter <UInt32>] [-Provider <ProviderType>] [[-Path] <String[]>]
 [-Flush] [<CommonParameters>]
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

### -Flush

{{ Fill Flush Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LevelFilter

{{ Fill LevelFilter Description }}

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

### -Path

{{ Fill Path Description }}

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Provider

{{ Fill Provider Description }}

```yaml
Type: Microsoft.Windows.DeliveryOptimization.AdminCommands.ProviderType
Parameter Sets: (All)
Aliases:
Accepted values: Dosvc, Domgmt

Required: False
Position: Named
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

### System.String[]

## OUTPUTS

### Microsoft.Windows.DeliveryOptimization.AdminCommands.LogOutput

## NOTES

## RELATED LINKS
