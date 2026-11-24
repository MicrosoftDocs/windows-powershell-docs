---
description: The Get-NetworkControllerManagedDevices cmdlet gets managed devices for a Network Controller.
external help file: Debug-NetworkController.psm1-help.xml
Module Name: NetworkControllerDiagnostics
ms.date: 10/22/2021
online version: https://learn.microsoft.com/powershell/module/networkcontrollerdiagnostics/get-networkcontrollermanageddevices?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerManagedDevices
---

# Get-NetworkControllerManagedDevices

## SYNOPSIS
Gets managed devices for a Network Controller.

## SYNTAX

```
Get-NetworkControllerManagedDevices [-RestURI] <String> [[-Credential] <PSCredential>]
 [[-CertificateThumbprint] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerManagedDevices** cmdlet gets managed devices for a Network Controller. The cmdlet aggregates results for devices from **Get-NetworkControllerServer**, **Get-NetworkControllerVirtualServer**, **Get-NetworkControllerGateway**, and **Get-NetworkControllerLoadBalancerMux**, and then presents the connections information for every device.

## EXAMPLES

### Example 1: Get managed devices
```powershell
Get-NetworkControllerManagedDevices -RestURI "https://nc.contoso.cloud.com"
```

This command gets managed devices for the specified Network Controller REST APIs.

## PARAMETERS

### -CertificateThumbprint
Certificate thumbprint to use for Network Controller.
Specify in case of certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Credential to use for Network Controller.
Specify in case of Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestURI
The URI to be used for Network Controller REST APIs.
Specify in case of wild card certificate deployment.

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

[Debug-NetworkControllerConfigurationState](Debug-NetworkControllerConfigurationState.md)

[Debug-ServiceFabricNodeStatus](Debug-ServiceFabricNodeStatus.md)

[Get-NetworkControllerDeploymentInfo](Get-NetworkControllerDeploymentInfo.md)

[Get-NetworkControllerGateway](../networkcontroller/Get-NetworkControllerGateway.md)

[Get-NetworkControllerLoadBalancerMux](../networkcontroller/Get-NetworkControllerLoadBalancerMux.md)

[Get-NetworkControllerServer](../networkcontroller/Get-NetworkControllerServer.md)

[Get-NetworkControllerVirtualServer](../networkcontroller/Get-NetworkControllerVirtualServer.md)
