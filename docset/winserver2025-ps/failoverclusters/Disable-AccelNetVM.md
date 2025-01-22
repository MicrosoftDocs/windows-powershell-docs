---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/01/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/disable-accelnetvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AccelNetVM
---

# Disable-AccelNetVM

## SYNOPSIS
Disables Accelerated Networking on a VM.

## SYNTAX

```
Disable-AccelNetVM [-VMName] <String> [<CommonParameters>]
```

## DESCRIPTION

Disables Accelerated Networking on a VM.

## EXAMPLES

### EXAMPLE 1

```powershell
Disable-AccelNetVM -VMName "MyVM"
```

This example disables Accelerated Networking for the VM named `MyVM`.

## PARAMETERS

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

[Enable-AccelNetVM](enable-accelnetvm.md)

[Get-AccelNetVM](get-accelnetvm.md)

[Set-AccelNetVM](set-accelnetvm.md)
