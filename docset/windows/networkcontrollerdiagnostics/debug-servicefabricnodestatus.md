---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Debug-ServiceFabricNodeStatus-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Debug-ServiceFabricNodeStatus
ms.reviewer:
ms.assetid: 9519481B-276C-49C5-AB86-220B7925D828
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Debug-NetworkController](./Debug-NetworkController.md)

[Debug-NetworkControllerConfigurationState](./Debug-NetworkControllerConfigurationState.md)

