---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollervirtualgatewaybgppeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVirtualGatewayBgpPeer
---

# Get-NetworkControllerVirtualGatewayBgpPeer

## SYNOPSIS
Gets a BGP peer.

## SYNTAX

```
Get-NetworkControllerVirtualGatewayBgpPeer [-VirtualGatewayId] <String[]> [-BgpRouterName] <String[]>
 [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVirtualGatewayBgpPeer** cmdlet gets the configuration of the Border Gateway Protocol (BGP) peer configuration for the peer(s) specified by the *ResourceId* parameter.
If you do not specify the *ResourceId*, this cmdlet gets the configuration for all BGP peers of the tenant.

## EXAMPLES

### Example 1: Display all BGP peer configurations for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayBgpPeer -ConnectionUri https://networkcontroller -VirtualGatewayId "Contoso" -BgpRouterName "Contoso_Vnet_Router1"
ResourceMetadata :
ResourceRef      : /VirtualGateways/Contoso/BgpRouters/Contoso_Vnet_Router1/BgpPeers/Contoso_SiteB_Gre
InstanceId       : 75320697-f1f9-486a-867c-cdc89ca3d958
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceId       : Contoso_SiteB_Gre
Properties       : Microsoft.Windows.NetworkController.VGwBgpPeerProperties
ResourceMetadata :
ResourceRef      : /VirtualGateways/Contoso/BgpRouters/Contoso_Vnet_Router1/BgpPeers/Contoso_SiteC_L3
InstanceId       : 0e36be61-11b5-4764-b64e-5e5181689c69
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceId       : Contoso_SiteC_L3
Properties       : Microsoft.Windows.NetworkController.VGwBgpPeerProperties
```

This command retrieves all the BGP peers for virtual gateway Contoso configured with the Network Controller where the BGP router is Contoso_Vnet_Router1.

### Example 2: Display a specified BGP peer configuration for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayBgpPeer -ConnectionUri "https://networkcontroller" -VirtualGatewayId "Contoso" -BgpRouterName "Contoso_Vnet_Router1" -ResourceId "Contoso_SiteB_Gre"
ResourceMetadata :
ResourceRef      : /VirtualGateways/Contoso/BgpRouters/Contoso_Vnet_Router1/BgpPeers/Contoso_SiteB_Gre
InstanceId       : 75320697-f1f9-486a-867c-cdc89ca3d958
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceId       : Contoso_SiteB_Gre
Properties       : Microsoft.Windows.NetworkController.VGwBgpPeerProperties
```

This command retrieves the BGP peer configuration for tenant Contoso where the router is Contoso_Vnet_Router1 and the peer name is Contoso_SiteB_Gre.

## PARAMETERS

### -BgpRouterName
Specifies an array of names of BGP routers.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Specifies an array of resource IDs of BGP peers.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

###  System.Object

This cmdlet returns object(s) that contain the following fields:

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a virtual/tenant gateway's BGP peer):
  - Provisioning state.
  - Peer BGP router IP address.
  - Peer BGP router autonomous system (AS) number.
  - Peer BGP router extended AS number.
  - Peer connection state.
  - Connectivity statistics.
  - Whether the BGP peer is automatically generated.
  - Array of BGP routing policy maps applied to the peers in ingress/egress direction.

## NOTES

## RELATED LINKS

[New-NetworkControllerVirtualGatewayBgpPeer](./New-NetworkControllerVirtualGatewayBgpPeer.md)

[Remove-NetworkControllerVirtualGatewayBgpPeer](./Remove-NetworkControllerVirtualGatewayBgpPeer.md)

