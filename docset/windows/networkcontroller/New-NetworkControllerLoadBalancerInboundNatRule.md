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
title: New-NetworkControllerLoadBalancerInboundNatRule
ms.reviewer:
ms.assetid: 879A1735-E0E5-49AA-8095-97BDBEFD720E
---

# New-NetworkControllerLoadBalancerInboundNatRule

## SYNOPSIS

This cmdlet adds/updates an inbound NAT rule associated with a load balancer resource.

## SYNTAX

```
New-NetworkControllerLoadBalancerInboundNatRule -ConnectionUri <Uri> -LoadBalancerId <string>
 -Properties <LoadBalancerInboundNatRuleProperties> -ResourceId <string> [-CertificateThumbPrint <string>]
 [-Credential <PSCredential>] [-Etag <string>] [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds/updates an inbound NAT rule associated with a load balancer resource.
This can be used to forward external traffic to a specific VM in the virtual network

## EXAMPLES

### Example 1

This example creates an inbound NAT rule named natRule1 for a load balancer resource called lb1.
The NAT rule specifies frontend and backend port as 3389 and protocol as TCP


```
//Retrieve the load balancer frontend IP configured beforehand
$frontEndIp=Get-NetworkControllerLoadBalancerFrontendIpConfiguration -ConnectionUri https://networkcontroller -LoadBalancerId lb1

//Retrieve the backend IPs for the NAT rule
$backEndIp=Get-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1

//Define the properties of the NAT rule
$natRule = New-Object Microsoft.Windows.NetworkController.LoadBalancerInboundNatRuleProperties
$natRule.backEndIpConfiguration=$backEndIp
$natRule.backEndPort=3389
$natRule.FrontEndIpConfiguration=$frontEndIp
$natRule.FrontEndPort=3389
$natRule.IdleTimeoutInMinutes=5
$natRule.Protocol="TCP"
New-NetworkControllerLoadBalancerInboundNatRule -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId natRule1 -Properties $natRule
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
Specifies the load balancer resource where the inbound NAT rule belongs

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
Specifies the properties of the inbound NAT rule:
1.
Front end port
2.
Back end port
3.
Whether floating IP is enabled
4.
Idle timeout (in minutes)
5.
Protocol
6.
Back end IP addresses behind the NAT
7.
Front end IP for the NAT

```yaml
Type: LoadBalancerInboundNatRuleProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique ID of the inbound NAT rule

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
Following properties can be added/changed for an inbound NAT rule:
1.
Front end port
2.
Back end port
3.
Whether floating IP is enabled
4.
Idle timeout (in minutes)
5.
Protocol
6.
Back end IP addresses behind the NAT
7.
Front end IP for the NAT

## OUTPUTS

## NOTES
## RELATED LINKS

