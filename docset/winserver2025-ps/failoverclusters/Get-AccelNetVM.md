---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/22/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-accelnetvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AccelNetVM
---

# Get-AccelNetVM

## SYNOPSIS
Gets VMs with Accelerated Networking.

## SYNTAX

```
Get-AccelNetVM [[-VMName] <String>] [[-VM] <VirtualMachineBase>] [<CommonParameters>]
```

## DESCRIPTION

Get VMs with Accelerated Networking.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-AccelNetVM -VMName "MyVM"
```

This example retrieves a VM named `MyVM`.

If no VM name is provided, all VM names are retrieved.

### EXAMPLE 2

```powershell
$vm = Get-VM -Name "MyVM"
Get-AccelNetVM -VM $vm
```

This example retrieves the VM object for a VM named `MyVM`.

## PARAMETERS

### -VMName

The Virtual Machine name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM

The VM object.

```yaml
Type: VirtualMachineBase
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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

[Set-AccelNetVM](set-accelnetvm.md)
