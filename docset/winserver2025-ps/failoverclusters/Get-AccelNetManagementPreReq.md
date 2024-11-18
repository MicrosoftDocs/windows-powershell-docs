---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/01/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-accelnetmanagementprereq?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AccelNetManagementPreReq
---

# Get-AccelNetManagementPreReq

## SYNOPSIS
Informs the user if the cluster nodes support Accelerated Networking.

## SYNTAX

```
Get-AccelNetManagementPreReq [[-IntentName] <String>] [<CommonParameters>]
```

## DESCRIPTION

Retrieves information if the cluster nodes support Accelerated Networking, including verifying OS
version and hyperthreading status.

## EXAMPLES

### Example 1

```powershell
Get-AccelNetManagementPreReq -IntentName "MyIntent"
```

This example checks if the cluster nodes support AccelNet for the intent named `MyIntent`.

## PARAMETERS

### -IntentName

The intent name to be used for Accelerated Networking Management. This parameter is required.

This value must be an integer greater than or equal to **0** and less than or equal to **99**.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-AccelNetManagement](disable-accelnetmanagement.md)

[Enable-AccelNetManagement](enable-accelnetmanagement.md)
