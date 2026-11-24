---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/22/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/enable-accelnetmanagement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AccelNetManagement
---

# Enable-AccelNetManagement

## SYNOPSIS
Enables Accelerated Networking Management cluster-wide.

## SYNTAX

```
Enable-AccelNetManagement [-IntentName] <String> [[-NodeReservePercentage] <UInt32>]
 [<CommonParameters>]
```

## DESCRIPTION

Enables AccelNet Management cluster-wide. Also sets the number of nodes to reserve and enables the
provided intent for AccelNet Management.

## EXAMPLES

### EXAMPLE 1

```powershell
Enable-AccelNetManagement -IntentName "MyIntent" -NodeReservePercentage 25
```

This example enables the `MyIntent` intent for Accelerated Networking Management and reserves `25`
percent of the nodes for that purpose. If the command is successful, it will return `$true`. If
there is an error, it will return `$false`.

## PARAMETERS

### -IntentName

The intent name to be used for Accelerated Networking Management. This parameter is required.

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

If this parameter is left blank, a default of **50%** will be assigned.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: $NODE_RESERVE_PERCENTAGE_DEFAULT
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

[Get-AccelNetManagement](get-accelnetmanagement.md)

[Get-AccelNetManagementPreReq](get-accelnetmanagementprereq.md)

[Set-AccelNetManagement](set-accelnetmanagement.md)
