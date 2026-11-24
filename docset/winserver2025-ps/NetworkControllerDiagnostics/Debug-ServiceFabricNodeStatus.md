---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Debug-ServiceFabricNodeStatus.psm1-help.xml
Module Name: NetworkControllerDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontrollerdiagnostics/debug-servicefabricnodestatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-ServiceFabricNodeStatus
---

# Debug-ServiceFabricNodeStatus

## SYNOPSIS
Queries the Network Controller Service Fabric to show the replication status and health state of each Network Controller node.

## SYNTAX

```
Debug-ServiceFabricNodeStatus [-ServiceTypeName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Debug-ServiceFabricNodeStatus** cmdlet queries the Network Controller Service Fabric to show the replication status and health state of each Network Controller node.
It also shows evolution of the status of the nodes by regularly polling for changes.

You can run this cmdlet from one of the Network Controller nodes.

## EXAMPLES

### Example 1: Get the replication status Virtual Switch Service
```
PS C:\>Debug-ServiceFabricNodeStatus -ServiceTypeName "VSwitchService"
```

This command gets the replication status VSwitchService, or Virtual Switch Service.

## PARAMETERS

### -ServiceTypeName
Specifies the service type that this cmdlet queries.
The acceptable values for this parameter are:

- ControllerService
- ApiService
- SlbManagerService
- ServiceInsertion
- FirewallService
- VSwitchService
- GatewayManager
- MonitoringService
- TopologyService
- FnmService
- HelperService
- UpdateService

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Debug-NetworkController](./Debug-NetworkController.md)

[Debug-NetworkControllerConfigurationState](./Debug-NetworkControllerConfigurationState.md)

