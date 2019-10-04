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
title: New-NetworkControllerNetworkInterfaceIpConfiguration
ms.reviewer:
ms.assetid: 3DF29F04-CFE0-4083-827B-4DA64CFF7971
---

# New-NetworkControllerNetworkInterfaceIpConfiguration

## SYNOPSIS

This cmdlet adds/updates an IP configuration to a network interface in the Network Controller

## SYNTAX

```
New-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri <Uri> -NetworkInterfaceId <string>
 -Properties <NetworkInterfaceIpConfigurationProperties> -ResourceId <string> [-CertificateThumbPrint <string>]
 [-Credential <PSCredential>] [-Etag <string>] [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds/updates an IP configuration to a network interface in the Network Controller

## EXAMPLES

### Example 1

This example creates an IP configuration resource named IP1 for a network interface named nw1.
The private IP Address is 10.0.0.1 and the IP allocation method is static.

```
$IpProp=New-Object Microsoft.Windows.NetworkController.NetworkInterfaceIpConfigurationPropertiesllocation
$IpProp.PrivateIpAddress="10.0.0.1"
$IpProp.PrivateIpAllocationMethod="Static"
$subnet=Get-NetworkControllerVirtualSubnet -ConnectionUri https://networkcontroller -VirtualNetworkId vnet1 -ResourceId Subnet1
$IpProp.Subnet=$subnet

New-NetworkControllerNetworkInterfaceIpconfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1 -ResourceId Ip1 -Properties $IpProp
```

## PARAMETERS

### -CertificateThumbPrint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.
This thumbprint must also be provided in the ClientCertificateThumbprint parameter in the Install-NetworkController or Set-NetworkController cmdlet so that Network Controller can authorize this user.

```yaml
Type: string
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
The default value is the current user.This user must be present in the security group provided in the ClientSecurityGroup parameter in the Install-NetworkController cmdlet.

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
Specifies the entity tag (ETag) parameter of the resource.
An ETag (entity tag) is an HTTP response header returned by an HTTP-compliant web server used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

```yaml
Type: string
Parameter Sets: (All)
Aliases: 
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: switch
Parameter Sets: (All)
Aliases: 
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterfaceId
Specifies the network interface where the IP configuration resource belongs

```yaml
Type: string
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
Following properties of a network interface can be added/updated:
1.
Private IP address
2.
Private IP address allocation method
3.
Subnet associated with the IP configuration

```yaml
Type: NetworkInterfaceIpConfigurationProperties
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique identifier of the resource

```yaml
Type: string
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceMetadata
This parameter contains metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases: 
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### 
Following properties of a network interface can be added/updated:
1.
Private IP address
2.
Private IP address allocation method
3.
Subnet associated with the IP configuration

## OUTPUTS

## NOTES

## RELATED LINKS

