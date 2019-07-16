---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-NetworkControllerReplica-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetworkControllerReplica
ms.reviewer:
ms.assetid: DAE30A55-2942-49AA-9F3A-2C00EA9F5D46
---

# Get-NetworkControllerReplica

## SYNOPSIS
Determines which node the Network Controller service modules use as primary.

## SYNTAX

```
Get-NetworkControllerReplica [[-ServiceTypeName] <String>] [-AllReplicas] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerReplica** cmdlet queries the Network Controller Service Fabric to determine which node a Network Controller service module uses as primary.
The service modules include SDNAPI and SlbManagerService.
This cmdlet also checks whether there is a quorum of service module replicas.
A quorum is required for consensus and correct operation.

You can run this cmdlet from one of the Network Controller nodes.

## EXAMPLES

### Example 1: Determine which node is primary for Virtual Switch Service
```
PS C:\>Get-NetworkControllerReplica -ServiceTypeName "VSwitchService"
```

This command determines which node is primary for VSwitchService, or the Virtual Switch Service.

## PARAMETERS

### -AllReplicas
Indicates that this cmdlet queries all replicas for only the primaries.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

Required: False
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

[Get-NetworkControllerDeploymentInfo](./Get-NetworkControllerDeploymentInfo.md)

