---
author: Kateyanne
description: 
external help file: 
manager: jasgro
Module Name: RDMgmt
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/rdmgmt/get-rddeploymentgatewayconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDDeploymentGatewayConfiguration
---

# Get-RDDeploymentGatewayConfiguration

## SYNOPSIS
Gets configuration settings for the RD Gateway for a Remote Desktop deployment.

## SYNTAX

```
Get-RDDeploymentGatewayConfiguration [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDDeploymentGatewayConfiguration** cmdlet gets configuration settings for the Remote Desktop Gateway (RD Gateway) for a Remote Desktop deployment.

## EXAMPLES

### Example 1: Retrieve Configuration Settings for the RD Gateway
```
PS C:\> Get-RDDeploymentGatewayConfiguration -ConnectionBroker "rdcb.contoso.com"
```

This command retrieves the configuration settings of the RD Gateway server associated with the RD Connection Broker server named rdcb.contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
Gatewaymode (String) - One of these values: Automatic, DoNotUse or Custom.

LogonMethod (String) - One of these values: Password, Smartcard or AllowUserToSelectRuntime.

GatewayExternalFQDN - External FQDN of the RD Gateway server specified for the deployment.

## NOTES

## RELATED LINKS

[Set-RDDeploymentGatewayConfiguration](./Set-RDDeploymentGatewayConfiguration.md)

