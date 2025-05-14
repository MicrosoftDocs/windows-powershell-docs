---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollervirtualgatewaynetworkconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerVirtualGatewayNetworkConnection
---

# New-NetworkControllerVirtualGatewayNetworkConnection

## SYNOPSIS
Creates a virtual gateway network connection.

## SYNTAX

```
New-NetworkControllerVirtualGatewayNetworkConnection [-VirtualGatewayId] <String> [-ResourceId] <String>
 [-Properties] <NetworkConnectionProperties> [[-ResourceMetadata] <ResourceMetadata>] [[-Etag] <String>]
 [-Force] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerVirtualGatewayNetworkConnection** cmdlet adds a configuration for a network connection for the specified tenant in Network Controller.
If a network connection configuration already exists, this cmdlet overwrites and replaces the older configuration.

## EXAMPLES

### Example 1: Add a new IPSec network connection to tenant virtual gateway
```
PS C:\> $uri = "https://networkcontroller"

# Create a new object for tenant network connection
PS C:\> $nwConnectionProperties = New-Object Microsoft.Windows.NetworkController.NetworkConnectionProperties

# Update the common object properties
PS C:\> $nwConnectionProperties.ConnectionType = "IPSec"
PS C:\> $nwConnectionProperties.OutboundKiloBitsPerSecond = 10000
PS C:\> $nwConnectionProperties.InboundKiloBitsPerSecond = 10000

# Update specific properties depending on the connection type
PS C:\> $nwConnectionProperties.IpSecConfiguration = New-Object Microsoft.Windows.NetworkController.IpSecConfiguration
PS C:\> $nwConnectionProperties.IpSecConfiguration.AuthenticationMethod = "PSK"
PS C:\> $nwConnectionProperties.IpSecConfiguration.SharedSecret = "P@ssw0rd"

PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode = New-Object Microsoft.Windows.NetworkController.QuickMode
PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode.PerfectForwardSecrecy = "PFS2048"
PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode.AuthenticationTransformationConstant = "SHA256128"
PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode.CipherTransformationConstant = "DES3"
PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode.SALifeTimeSeconds = 1233
PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode.IdleDisconnectSeconds = 500
PS C:\> $nwConnectionProperties.IpSecConfiguration.QuickMode.SALifeTimeKiloBytes = 2000

PS C:\> $nwConnectionProperties.IpSecConfiguration.MainMode = New-Object Microsoft.Windows.NetworkController.MainMode
PS C:\> $nwConnectionProperties.IpSecConfiguration.MainMode.DiffieHellmanGroup = "Group2"
PS C:\> $nwConnectionProperties.IpSecConfiguration.MainMode.IntegrityAlgorithm = "SHA256"
PS C:\> $nwConnectionProperties.IpSecConfiguration.MainMode.EncryptionAlgorithm = "AES256"
PS C:\> $nwConnectionProperties.IpSecConfiguration.MainMode.SALifeTimeSeconds = 1234
PS C:\> $nwConnectionProperties.IpSecConfiguration.MainMode.SALifeTimeKiloBytes = 2000

# L3 specific configuration (leave blank for IPSec)
PS C:\> $nwConnectionProperties.IPAddresses = @()
PS C:\> $nwConnectionProperties.PeerIPAddresses = @()

# Update the IPv4 routes that are reachable over the site-to-site VPN tunnel
PS C:\> $nwConnectionProperties.Routes = @()
PS C:\> $ipv4Route = New-Object Microsoft.Windows.NetworkController.RouteInfo
PS C:\> $ipv4Route.DestinationPrefix = "14.1.10.1/32"
PS C:\> $ipv4Route.metric = 10
PS C:\> $nwConnectionProperties.Routes += $ipv4Route

# Tunnel destination (remote endpoint) address
PS C:\> $nwConnectionProperties.DestinationIPAddress = "10.127.134.121"

# Add the new network connection for the tenant
PS C:\> New-NetworkControllerVirtualGatewayNetworkConnection -ConnectionUri $uri -VirtualGatewayId "Contoso" -ResourceId "Contoso_IPSecGW" -Properties $nwConnectionProperties -Force
```

This set of cmdlets adds a new IPSec connection on the Contoso tenant virtual gateway.

### Example 2: Add a GRE network connection to a tenant virtual gateway
```
PS C:\> $uri = "https://networkcontroller"

# Create a new object for the tenant network connection
PS C:\> $nwConnectionProperties = New-Object Microsoft.Windows.NetworkController.NetworkConnectionProperties

# Update the common object properties
PS C:\> $nwConnectionProperties.ConnectionType = "GRE"
PS C:\> $nwConnectionProperties.OutboundKiloBitsPerSecond = 10000
PS C:\> $nwConnectionProperties.InboundKiloBitsPerSecond = 10000

# Update specific properties depending on the connection type
PS C:\> $nwConnectionProperties.GreConfiguration = New-Object Microsoft.Windows.NetworkController.GreConfiguration
PS C:\> $nwConnectionProperties.GreConfiguration.GreKey = 1234

# Update the IPv4 routes that are reachable over the site-to-site VPN tunnel
PS C:\> $nwConnectionProperties.Routes = @()
PS C:\> $ipv4Route = New-Object Microsoft.Windows.NetworkController.RouteInfo
PS C:\> $ipv4Route.DestinationPrefix = "14.2.20.1/32"
PS C:\> $ipv4Route.metric = 10
PS C:\> $nwConnectionProperties.Routes += $ipv4Route

# Tunnel destination (remote endpoint) address
PS C:\> $nwConnectionProperties.DestinationIPAddress = "10.127.134.122"

# L3 specific configuration (leave blank for GRE)
PS C:\> $nwConnectionProperties.L3Configuration = New-Object Microsoft.Windows.NetworkController.L3Configuration
PS C:\> $nwConnectionProperties.IPAddresses = @()
PS C:\> $nwConnectionProperties.PeerIPAddresses = @()

# Add the new network connection for the tenant
PS C:\> New-NetworkControllerVirtualGatewayNetworkConnection -ConnectionUri $uri -VirtualGatewayId "Contoso" -ResourceId "Contoso_GreGW" -Properties $nwConnectionProperties -Force
```

This set of cmdlets adds a new GRE connection on Contoso tenant virtual gateway.

### Example 3: Add a new GRE network connection to a tenant virtual gateway
```
PS C:\> $uri = "https://networkcontroller"

#############################################################################
# A. Configure a VNET based Logical Network for the L3 Connection on the NC #
#############################################################################

# Create a new object for the logical network to be used for L3 forwarding
PS C:\> $lnProperties = New-Object Microsoft.Windows.NetworkController.LogicalNetworkProperties

PS C:\> $lnProperties.NetworkVirtualizationEnabled = $false
PS C:\> $lnProperties.Subnets = @()

# Create a new object for the logical subnet to be used for L3 forwarding and update properties
PS C:\> $logicalsubnet = New-Object Microsoft.Windows.NetworkController.LogicalSubnet
PS C:\> $logicalsubnet.ResourceId = "Contoso_L3_Subnet"
PS C:\> $logicalsubnet.Properties = New-Object Microsoft.Windows.NetworkController.LogicalSubnetProperties
PS C:\> $logicalsubnet.Properties.VlanID = 1001
PS C:\> $logicalsubnet.Properties.AddressPrefix = "10.127.134.0/25"
PS C:\> $logicalsubnet.Properties.DefaultGateway = "10.127.134.1"

$lnProperties.Subnets += $logicalsubnet

# Add the new logical network to Network Controller
PS C:\> $vlanNetwork = New-NetworkControllerLogicalNetwork -ConnectionUri $uri -ResourceId "Contoso_L3_Network" -Properties $lnProperties -Force

#######################################################
# B. Configure the L3 Forwarding connection on the NC #
#######################################################
# Create a new object for the tenant network connection
PS C:\> $nwConnectionProperties = New-Object Microsoft.Windows.NetworkController.NetworkConnectionProperties

# Update the common object properties
PS C:\> $nwConnectionProperties.ConnectionType = "L3"
PS C:\> $nwConnectionProperties.OutboundKiloBitsPerSecond = 10000
PS C:\> $nwConnectionProperties.InboundKiloBitsPerSecond = 10000

# GRE-specific configuration (leave blank for L3)
PS C:\> $nwConnectionProperties.GreConfiguration = New-Object Microsoft.Windows.NetworkController.GreConfiguration

# Update specific properties depending on the connection type
PS C:\> $nwConnectionProperties.L3Configuration = New-Object Microsoft.Windows.NetworkController.L3Configuration
PS C:\> $nwConnectionProperties.L3Configuration.VlanSubnet = $vlanNetwork.properties.Subnets[0]

PS C:\> $nwConnectionProperties.IPAddresses = @()
PS C:\> $localIPAddress = New-Object Microsoft.Windows.NetworkController.CidrIPAddress
PS C:\> $localIPAddress.IPAddress = "10.127.134.55"
PS C:\> $localIPAddress.PrefixLength = 25
PS C:\> $nwConnectionProperties.IPAddresses += $localIPAddress

PS C:\> $nwConnectionProperties.PeerIPAddresses = @("10.127.134.65")

# Update the IPv4 routes that are reachable over the site-to-site VPN tunnel
PS C:\> $nwConnectionProperties.Routes = @()
PS C:\> $ipv4Route = New-Object Microsoft.Windows.NetworkController.RouteInfo
PS C:\> $ipv4Route.DestinationPrefix = "14.2.20.1/32"
PS C:\> $ipv4Route.metric = 10
PS C:\> $nwConnectionProperties.Routes += $ipv4Route

# Add the new network connection for the tenant
PS C:\> New-NetworkControllerVirtualGatewayNetworkConnection -ConnectionUri $uri -VirtualGatewayId "Contoso" -ResourceId "Contoso_L3GW" -Properties $nwConnectionProperties -Force
```

This set of cmdlets adds a new GRE connection on Contoso tenant virtual gateway.

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
Position: 6
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
Specifies the properties of the network connection.

```yaml
Type: NetworkConnectionProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the network connection to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualGatewayId
Specifies the ID of a virtual gateway.

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

### Microsoft.Windows.NetworkController.NetworkConnectionProperties

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

    ""ConnectionType"" : """",

    ""OutboundKiloBitsPerSecond"" : \<UInt32\>,

    ""InboundKiloBitsPerSecond"" : \<UInt32\>,

    ""IPSecConfiguration"": @{

        ""QuickMode"": @{

                ""PerfectForwardSecrecy"": """",

                ""authenticationTransformationConstant"": """",

                ""cipherTransformationConstant"": """",

                ""saLifeTimeSeconds"": """",

                ""idleDisconnectSeconds"": """",

                ""saLifeTimeKiloBytes"": """"

        },

        ""MainMode"": @{

            ""diffieHellmanGroup"": """",

            ""integrityAlgorithm"": """",

            ""encryptionAlgorithm"": """",

            ""saLifeTimeSeconds"": """",

            ""saLifeTimeKiloBytes"": """"

        },

        ""AuthenticationMethod"": """",

        ""SharedSecret"": """"

    },

    ""GreConfiguration"": @{ ""GREKey"": """"},

    ""L3Configuration"": @{ ""VlanSubnet"": @{""ResourceRef"": ""\<string\>"" }},

    ""IPAddresses"": @(),

    ""PeerIPAddresses"": @(),

    ""Routes"": @( @{

        ""DestinationPrefix"": """",

        ""Metric"": """"

    }),

    ""DestinationIPAddress"" : """"

}"


## NOTES

## RELATED LINKS

[Get-NetworkControllerVirtualGatewayNetworkConnection](./Get-NetworkControllerVirtualGatewayNetworkConnection.md)

[Remove-NetworkControllerVirtualGatewayNetworkConnection](./Remove-NetworkControllerVirtualGatewayNetworkConnection.md)

