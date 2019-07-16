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
title: New-NetworkControllerLoadBalancerFrontendIpConfiguration
ms.reviewer:
ms.assetid: 69EADC55-F391-4179-B0CB-701B3D6E2A9E
---

# New-NetworkControllerLoadBalancerFrontendIpConfiguration

## SYNOPSIS

This cmdlet adds/updates the front end IP configuration of a load balancer resource.

## SYNTAX

```
New-LoadBalancerFrontEndIpConfiguration -ConnectionUri <Uri> -LoadBalancerId <string>
 -Properties <LoadBalancerBackendAddressPoolProperties> -ResourceId <string> [-CertificateThumbPrint <string>]
 [-Credential <PSCredential>] [-Etag <string>] [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds/updates the front end IP configuration of a load balancer resource.
The front-end IP is commonly referred to as a Virtual IP (VIP).
The VIP must be taken from an unused IP in one of the logical network IP Pool which has been previously given to the load balancer manager.

## EXAMPLES

### Example 1

This example creates a front end IP configuration resource named frontEnd1 for a load balancer resource named lb1

```
//Retrieve the subnet for front end IP
$subnet = Get-NetworkControllerSubnet -ConnectionUri https://networkcontroller -NetworkId ln1 -ResourceId subnet1

//Create the front end IP resource
$frontEndIp=New-Object Microsoft.Windows.NetworkController.LoadBalancerFrontEndIpConfigurationProperties
$frontEndIp.PrivateIpAddress="10.127.32.12"
$frontEndIp.PrivateIPAllocationMethod="Static"

New-NetworkControllerLoadBalancerFrontEndIpConfiguration -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId frontEnd1 -Properties $frontEndIp
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

### -LoadBalancerId
Specifies the load balancer with which the resource is associated

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
Following properties can be added/updated for this resource:
1.
Private IP address (VIP) of the resource
2.
Private IP address allocation method
3.
Subnet with which the resource is associated

```yaml
Type: LoadBalancerBackendAddressPoolProperties
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
Following properties can be added/updated for this resource:
1.
Private IP address (VIP) of the resource
2.
Private IP address allocation method
3.
Subnet with which the resource is associated

## OUTPUTS

## NOTES
## RELATED LINKS

