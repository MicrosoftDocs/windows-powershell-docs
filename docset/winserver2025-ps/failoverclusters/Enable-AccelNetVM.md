---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/22/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/enable-accelnetvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AccelNetVM
---

# Enable-AccelNetVM

## SYNOPSIS
Enables Accelerated Networking on a VM.

## SYNTAX

```
Enable-AccelNetVM [-VMName] <String> [-Performance] <PerformanceWeight> [<CommonParameters>]
```

## DESCRIPTION

Enables Accelerated Networking on a VM.

## EXAMPLES

### EXAMPLE 1

```powershell
Enable-AccelNetVM -VMName "MyVM" -Performance High
```

This example enables Accelerated Networking with the performance level set to `High` for the VM
named `MyVM`.

## PARAMETERS

### -Performance

Sets the performance level. This parameter is required. Acceptable values are:

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

Specifies the name of the virtual machine. This parameter is required.

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

[Get-AccelNetVM](get-accelnetvm.md)

[Set-AccelNetVM](set-accelnetvm.md)
