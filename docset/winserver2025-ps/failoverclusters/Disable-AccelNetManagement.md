---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/01/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/disable-accelnetmanagement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AccelNetManagement
---

# Disable-AccelNetManagement

## SYNOPSIS
Disables Accelerated Networking Management cluster-wide.

## SYNTAX

```
Disable-AccelNetManagement [<CommonParameters>]
```

## DESCRIPTION

Disables Accelerated Networking Management cluster-wide. This doesn't turn off SR-IOV on VMs.

## EXAMPLES

### EXAMPLE 1

```powershell
Disable-AccelNetManagement
```

This example disables the Accelerated Networking Management layer on the cluster.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AccelNetManagement](enable-accelnetmanagement.md)

[Get-AccelNetManagementPreReq](get-accelnetmanagementprereq.md)
