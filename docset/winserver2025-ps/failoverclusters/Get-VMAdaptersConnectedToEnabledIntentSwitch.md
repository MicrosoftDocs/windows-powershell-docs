---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/22/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-vmadaptersconnectedtoenabledintentswitch?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMAdaptersConnectedToEnabledIntentSwitch
---

# Get-VMAdaptersConnectedToEnabledIntentSwitch

## SYNOPSIS
Gets the adapters on the VM that are connected to the enabled intent switch.

## SYNTAX

```
Get-VMAdaptersConnectedToEnabledIntentSwitch [[-VMName] <String>] [<CommonParameters>]
```

## DESCRIPTION

Retrieves the adapters on the VM that are connected to the enabled intent switch.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-VMAdaptersConnectedToEnabledIntentSwitch -VMName "MyVM"
```

This example retrieves the network adapter connected to the enabled intent switch from the VM named
`MyVM`.

## PARAMETERS

### -VMName

Specifies the name of the virtual machine.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
