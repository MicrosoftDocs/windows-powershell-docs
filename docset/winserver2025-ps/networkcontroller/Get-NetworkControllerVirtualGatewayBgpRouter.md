---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollervirtualgatewaybgprouter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVirtualGatewayBgpRouter
---

# Get-NetworkControllerVirtualGatewayBgpRouter

## SYNOPSIS
Gets a BGP router.

## SYNTAX

```
Get-NetworkControllerVirtualGatewayBgpRouter [-VirtualGatewayId] <String[]> [[-ResourceId] <String[]>]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVirtualGatewayBgpRouter** cmdlet gets the configuration of the Border Gateway Protocol (BGP) router(s) specified by the *ResourceId* parameter.
If you do not specify the *ResourceId*, this cmdlet gets all BGP routers for the tenant.

## EXAMPLES

### Example 1: Display all BGP router configurations for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayBgpRouter -ConnectionUri https://networkcontroller -VirtualGatewayId "Contoso"
ResourceMetadata :
ResourceRef      : /VirtualGateways/Contoso/BgpRouters/Contoso_Vnet_Router1
InstanceId       : a3e78792-f17a-4179-85b2-f04d9ef332d1
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceId       : Contoso_Vnet_Router1
Properties       : Microsoft.Windows.NetworkController.VGwBgpRouterProperties
ResourceMetadata :
ResourceRef      : /VirtualGateways/Contoso/BgpRouters/Contoso_Vnet_Router2
InstanceId       : 3a15667d-af0c-4092-a8b5-2e66131815a8
Etag             : W/"143d70dc-1bec-4171-88b1-c6957e2b7aad"
ResourceId       : Contoso_Vnet_Router2
Properties       : Microsoft.Windows.NetworkController.VGwBgpRouterProperties
```

This command retrieves all the BGP routers for the virtual gateway Contoso configured with the Network Controller.

### Example 2: Display a specified BGP router configuration for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayBgpPeer -ConnectionUri "https://networkcontroller" -VirtualGatewayId "Contoso" -ResourceId "Contoso_Vnet_Router1"
ResourceMetadata :
ResourceRef      : /VirtualGateways/Contoso/BgpRouters/Contoso_Vnet_Router1
InstanceId       : a3e78792-f17a-4179-85b2-f04d9ef332d1
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceId       : Contoso_Vnet_Router1
Properties       : Microsoft.Windows.NetworkController.VGwBgpRouterProperties
```

This command retrieves the tenant BGP router Contoso_Vnet_Router1.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.
This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies an array of resource IDs of BGP routers.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

This cmdlet returns object(s) that contain the following fields:

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a virtual/tenant gateway's BGP router):
  - Provisioning state.
  - BGP router identifier.
  - BGP router's local IP address(es).
  - BGP router's extended AS number.
  - Router connection state.
  - Whether the BGP peer is automatically generated.
  - Array of BGP peers configured on this router.

## NOTES

## RELATED LINKS

[New-NetworkControllerVirtualGatewayBgpRouter](./New-NetworkControllerVirtualGatewayBgpRouter.md)

[Remove-NetworkControllerVirtualGatewayBgpRouter](./Remove-NetworkControllerVirtualGatewayBgpRouter.md)

