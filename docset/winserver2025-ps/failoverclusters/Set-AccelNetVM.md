---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/01/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-accelnetvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AccelNetVM
---

# Set-AccelNetVM

## SYNOPSIS
Sets Accelerated Networking on a VM.

## SYNTAX

```
Set-AccelNetVM [-VMName] <String> [-Performance] <PerformanceWeight> [<CommonParameters>]
```

## DESCRIPTION

Sets Accelerated Networking on a VM.

## EXAMPLES

### EXAMPLE 1

```powershell
Set-AccelNetVM -VMName "MyVM" -Performance High
```

This example sets Accelerated Networking with the performance level set to `High` for the VM
named `MyVM`.

## PARAMETERS

### -Performance

Sets the performance level. Acceptable values are:

- `Low`
- `Medium`
- `High`

```yaml
Type: PerformanceWeight
Parameter Sets: (All)
Aliases:
Accepted values: Low, Medium, High

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName

Specifies the name of the virtual machine.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AccelNetVM](disable-accelnetvm.md)

[Enable-AccelNetVM](enable-accelnetvm.md)
