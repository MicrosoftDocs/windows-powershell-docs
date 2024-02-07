---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollervirtualgateway?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVirtualGateway
---

# Get-NetworkControllerVirtualGateway

## SYNOPSIS
Gets the configuration of one or more virtual gateways.

## SYNTAX

```
Get-NetworkControllerVirtualGateway [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVirtualGateway** cmdlet gets the virtual gateway configuration for one or more tenants specified by the *ResourceId* parameter.
If you do not specify the *ResourceId*, this cmdlet gets all virtual gateways for all tenants.

## EXAMPLES

### Example 1: Display all virtual gateway configurations
```
PS C:\> Get-NetworkControllerVirtualGateway -ConnectionUri "https://networkcontroller"
Tags             :
ResourceRef      : /VirtualGateways/Contoso
InstanceId       : 49931c9d-8d5e-47a0-8c2c-7b5d597e9bc1
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceMetadata :
ResourceId       : Contoso
Properties       : Microsoft.Windows.NetworkController.VirtualGatewayProperties
Tags             :
ResourceRef      : /VirtualGateways/Woodgrove
InstanceId       : ad2b0c59-7eb4-4851-b0ef-0181376b622c
Etag             : W/"09d07a70-0ae1-4914-9bd5-76d53ff06659"
ResourceMetadata :
ResourceId       : Woodgrove
Properties       : Microsoft.Windows.NetworkController.VirtualGatewayProperties
```

This command gets all virtual gateways configured with the Network Controller.

### Example 2: Display a specified virtual gateway configuration
```
PS C:\> Get-NetworkControllerVirtualGateway -ConnectionUri "https://networkcontroller" -ResourceId "Contoso"
Tags             :
ResourceRef      : /VirtualGateways/Contoso
InstanceId       : 49931c9d-8d5e-47a0-8c2c-7b5d597e9bc1
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceMetadata :
ResourceId       : Contoso
Properties       : Microsoft.Windows.NetworkController.VirtualGatewayProperties
```

This command gets the virtual gateway configuration for the tenant Contoso.

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
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

The thumbprint must be provided only if the network controller client authentication is X509 certificates.
**Get-NetworkController** retrieves that client authentication and authorization information.

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
Specifies an array of resource IDs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
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

This cmdlet returns objects that contain the following fields.

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a virtual gateway/tenant gateway):
  - Reference to the virtual network IP subnet used for routing between gateway and virtual network.
  - Array of network connections configured in the virtual gateway.
  - Routing type configured for CA space routing.
  - Array of CA space BGP routers configured in the virtual gateway and their configurations.
  - Array of BGP routing policy maps configured for the tenant.
  - Array of references to gateway pools where the virtual gateway is configured.

## NOTES

## RELATED LINKS

[New-NetworkControllerVirtualGateway](./New-NetworkControllerVirtualGateway.md)

[Remove-NetworkControllerVirtualGateway](./Remove-NetworkControllerVirtualGateway.md)

