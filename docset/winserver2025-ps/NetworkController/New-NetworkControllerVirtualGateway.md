---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollervirtualgateway?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerVirtualGateway
---

# New-NetworkControllerVirtualGateway

## SYNOPSIS
Creates a virtual gateway.

## SYNTAX

```
New-NetworkControllerVirtualGateway [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <VirtualGatewayProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerVirtualGateway** cmdlet adds a new virtual gateway configuration for the specified tenant to the Network Controller.
If the virtual gateway configuration already exists with Network Controller, this cmdlet overwrites and replaces the older configuration.

## EXAMPLES

### Example 1: Add a new virtual gateway configuration to the Network Controller
```
PS C:\> $uri = "https://networkcontroller"

# Create a new object for tenant virtual gateway
PS C:\> $VirtualGWProperties = New-Object Microsoft.Windows.NetworkController.VirtualGatewayProperties

# Update gateway pool reference
PS C:\> $VirtualGWProperties.GatewayPools = @()
PS C:\> $VirtualGWProperties.GatewayPools += $gwPool

# Specify the Virtual Subnet to use for routing between the gateway and virtual network
PS C:\> $VirtualGWProperties.GatewaySubnets = @()
PS C:\> $VirtualGWProperties.GatewaySubnets += $RoutingSubnet

# Update the rest of the virtual gateway object properties
PS C:\> $VirtualGWProperties.RoutingType = "Dynamic"
PS C:\> $VirtualGWProperties.NetworkConnections = @()
PS C:\> $VirtualGWProperties.BgpRouters = @()

# Add the new virtual gateway for tenant
PS C:\> New-NetworkControllerVirtualGateway -ConnectionUri $uri -ResourceId "Woodgrove_VirtualGW" -Properties $VirtualGWProperties

Confirm
Performing the operation 'New-NetworkControllerVirtualGateway' on entities of type 'Microsoft.Windows.NetworkController.VirtualGateway' via
'https://networkcontroller/networking/v1/virtualgateways/Woodgrove_VirtualGW'. Are you sure you want to continue?
 [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): yes

Tags             :
ResourceRef      : /VirtualGateways/Woodgrove_VirtualGW
InstanceId       : 49931c9d-8d5e-47a0-8c2c-7b5d597e9bc1
Etag             : W/"b2e94f9d-c589-4c11-84dc-fc2241135352"
ResourceMetadata :
ResourceId       : Woodgrove_VirtualGW
Properties       : Microsoft.Windows.NetworkController.VirtualGatewayProperties
```

This set of cmdlets adds a new tenant virtual gateway configuration to Network Controller.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -Etag
Specifies the entity tag (ETag) of the resource.
An ETag is an HTTP response header returned by an HTTP-compliant web server.
An ETag is used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
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

### -Properties
Specifies the properties of a virtual gateway that this cmdlet adds or updates.

```yaml
Type: VirtualGatewayProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies an array of resource IDs of virtual gateways.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceMetadata
Specifies metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags


```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Windows.NetworkController.VirtualGatewayProperties

## OUTPUTS

### System.Object

This cmdlet outputs the following information:

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource:

"{

         ""GatewaySubnets"" : @(@{ ""ResourceRef"": ""\<string\>"" } ),
               ""NetworkConnections"": @(

                     @{ \<NetworkControllerVirtualGatewayNetworkConnection\>}

              ),

         ""RoutingType"": """",

         ""BgpRouters"": @(

                  @{\<NetworkControllerVirtualGatewayBgpRouter\>}

         ),

         ""PolicyMaps"": @(

                  @{\<NetworkControllerVirtualGatewayPolicyMap\>}

          ),

          ""GatewayPools"": @(@{ ""ResourceRef"": ""\<string\>"" } )

}"

## NOTES

## RELATED LINKS

[Get-NetworkControllerVirtualGateway](./Get-NetworkControllerVirtualGateway.md)

[Remove-NetworkControllerVirtualGateway](./Remove-NetworkControllerVirtualGateway.md)

