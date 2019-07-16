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
title: New-NetworkControllerLoadBalancerBackendAddressPool
ms.reviewer:
ms.assetid: 2A3E3173-627F-4DC5-953F-6DA4DF5E1302
---

# New-NetworkControllerLoadBalancerBackendAddressPool

## SYNOPSIS
This cmdlet adds/updates the configuration of a backend address pool resource associated with a load balancer.

## SYNTAX

```
New-NetworkControllerLoadBalancerBackendAddressPool -ConnectionUri <Uri> -LoadBalancerId <string>
 -Properties <LoadBalancerBackendAddressPoolProperties> -ResourceId <string> [-CertificateThumbPrint <string>]
 [-Credential <PSCredential>] [-Etag <string>] [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds/updates the configuration of a backend address pool resource associated with a load balancer.
The backend address pool contains the Dynamic IPs (DIPs) that make up the members of the load balanced set of VMs.

## EXAMPLES

### Example 1

```
//Retrieve the backend IPs that will form the pool
$backEndIp=Get-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1

//Define the properties of the backend address pool
$bePool = New-Object Microsoft.Windows.NetworkController.LoadBalancerBackendAddressPoolProperties
$bePool.backEndIpConfiguration=$backEndIp

New-NetworkControllerLoadBalancerBackEndAddressPool -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId be1 -Properties $bePool
```

Description

This example creates a backend address pool named be1 for a load balancer resource named lb1.
This address pool has the IP of network interface nw1 as the single member in the pool

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
Specifies the load balancer with which the backend address pool is associated

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
Specifies the IP configuration of the backend pool members

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
Specifies the unique identifier of the backend address pool

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

This takes backend IP configuration of the pool members as input

## OUTPUTS

## NOTES
## RELATED LINKS

