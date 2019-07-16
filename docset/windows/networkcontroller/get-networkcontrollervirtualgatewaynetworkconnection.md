---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetworkControllerVirtualGatewayNetworkConnection
ms.reviewer:
ms.assetid: 06D7BF46-F156-46C5-8278-CABE6655C5D8
---

# Get-NetworkControllerVirtualGatewayNetworkConnection

## SYNOPSIS
Gets a virtual gateway network connection.

## SYNTAX

```
Get-NetworkControllerVirtualGatewayNetworkConnection [-VirtualGatewayId] <String[]> [[-ResourceId] <String[]>]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVirtualGatewayNetworkConnection** cmdlet gets the configuration of one or more network connections for the specified virtual/tenant gateway.

If you do not specify a *ResourceId*, this cmdlet gets all network connections.

## EXAMPLES

### Example 1: Display all Network Connections configurations for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayNetworkConnection -ConnectionUri https://networkcontroller -VirtualGatewayId "Contoso"
```

This command retrieves all the Network Connections for the virtual gateway Contoso configured with the Network Controller.

### Example 2: Display a specified Network Connection configuration for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayNetworkConnection -ConnectionUri "https://networkcontroller" -VirtualGatewayId "Contoso" -ResourceId "IPSec_GW"
```

This command retrieves the Network Connection configuration for the tenant Contoso.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of the Network Controller, used by all Representational State Transfer (REST) clients to connect to Network Controller.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.
The default value is the current user.
This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException


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

### -ResourceId
Specifies an array of network connection resource IDs

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualGatewayId
Specifies an array of virtual gateway IDs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet returns object(s) that contains the following fields: 

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a virtual/tenant gateway's network connection). 
  - Network connection type (IPSec, GRE, L3).
  - Outbound bandwidth capacity. 
  - Inbound bandwidth capacity. 
  - Network connection (IPSec/GRE/L3) specific configuration details. 
  - Array of local IP addresses.
  - Array of remote peer IP addresses.
  - Array of customer routes, both static and dynamically learned. 
  - Connection status (enabled/disabled). 
  - Connection state (connected/disconnected). 
  - Connection up-time. 
  - Connection statistics.
  - Connection error reason.
  - Connection unreachability reason.
  - Source IP address. 
  - Remote destination IP address.
  - Reference to the gateway virtual machine where the connection is configured.

## NOTES

## RELATED LINKS

[New-NetworkControllerVirtualGatewayNetworkConnection](./New-NetworkControllerVirtualGatewayNetworkConnection.md)

[Remove-NetworkControllerVirtualGatewayNetworkConnection](./Remove-NetworkControllerVirtualGatewayNetworkConnection.md)

