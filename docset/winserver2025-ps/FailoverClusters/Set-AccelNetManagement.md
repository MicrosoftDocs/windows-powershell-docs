---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/22/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-accelnetmanagement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AccelNetManagement
---

# Set-AccelNetManagement

## SYNOPSIS
Sets Accelerated Networking Management cluster-wide.

## SYNTAX

```
Set-AccelNetManagement [[-IntentName] <String>] [[-NodeReservePercentage] <UInt32>]
 [<CommonParameters>]
```

## DESCRIPTION

Sets AccelNet Management cluster-wide. Also sets the number of nodes to reserve and enables the
provided intent for AccelNet Management. Returns `$true` upon success, and `$false` otherwise.

If AccelNet Management is currently active with a certain intent, providing a value for the
`-IntentName` parameter will disable the current AccelNet Management configuration. After disabling
the current AccelNet Management configuration, AccelNet Management is reenabled based on the
configuration of the new intent.

## EXAMPLES

### EXAMPLE 1

```powershell
Set-AccelNetManagement -IntentName "LowPerformance" -NodeReservePercentage 10
```

This example enables the `LowPerformance` intent for AccelNet Management and reserves `10` percent
of the nodes for that purpose. If the command is successful, it will return `$true`. If there is an
error, it will return `$false`.

## PARAMETERS

### -IntentName

The intent name to be used for AccelNet Management. This parameter is required.

This value must be an integer greater than or equal to **0** and less than or equal to **99**.

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

### -NodeReservePercentage

The percentage of cluster nodes that can be down simultaneously while still maintaining enough
virtual functions for each VM chosen for Accelerated Networking Management.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: 0
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

[Disable-AccelNetManagement](disable-accelnetmanagement.md)

[Enable-AccelNetManagement](enable-accelnetmanagement.md)

[Get-AccelNetManagement](get-accelnetmanagement.md)

[Get-AccelNetManagementPreReq](get-accelnetmanagementprereq.md)
