---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: New-NetworkControllerLoadBalancingRule
ms.reviewer:
ms.assetid: 476551A4-E2C3-47C2-84D0-4C99425B56BB
---

# New-NetworkControllerLoadBalancingRule

## SYNOPSIS

This cmdlet adds/updates a load balancing rule associated with a load balancer.

## SYNTAX

```
New-NetworkControllerLoadBalancingRule -ConnectionUri <Uri> -LoadBalancerId <string>
 -Properties <LoadBalancingRuleProperties> -ResourceId <string> [-CertificateThumbPrint <string>]
 [-Credential <PSCredential>] [-Etag <string>] [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds/updates a load balancing rule associated with a load balancer.
This load balancing rule defines how traffic that arrives at the front-end IP is to be sent to the backend IP

## EXAMPLES

### Example 1 - define a load balancing rule

```powershell
# Frontend
# Create the front end IP resource
$frontEndIp = New-Object Microsoft.Windows.NetworkController.LoadBalancerFrontEndIpConfigurationProperties
$frontEndIp.PrivateIpAddress="10.127.32.12"
$frontEndIp.PrivateIPAllocationMethod="Static"

$FrontEndIPConfig = New-NetworkControllerLoadBalancerFrontEndIpConfiguration -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId frontEnd1 -Properties $frontEndIp

# Backend
# Retrieve the backend IPs that will form the pool
$backEndIp = Get-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1

## Define the properties of the backend address pool
$bePool = New-Object Microsoft.Windows.NetworkController.LoadBalancerBackendAddressPoolProperties
$bePool.backEndIpConfiguration = $backEndIp

$BackEndAddressPool = New-NetworkControllerLoadBalancerBackEndAddressPool -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId be1 -Properties $bePool

# Probe
$ProbeProperties = New-Object Microsoft.Windows.NetworkController.LoadBalancerProbeProperties
$ProbeProperties.protocol="HTTP"
$ProbeProperties.port="80"
$ProbeProperties.RequestPath="/health.htm"
$ProbeProperties.IntervalInSeconds=5
$ProbeProperties.NumberofProbes=8
$Probe = New-NetworkControllerLoadBalancerProbe -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId Probe1 -Properties $ProbeProperties

# Rule properties
$RuleProperties = New-Object Microsoft.Windows.NetworkController.LoadBalancingRuleProperties
$RuleProperties.FrontEndIPConfigurations += $FrontEndIPConfig
$RuleProperties.BackendAddressPool = $BackEndAddressPool
$RuleProperties.protocol = "TCP"
$RuleProperties.FrontEndPort = 80
$RuleProperties.BackEndPort = 80
$RuleProperties.IdleTimeoutInMinutes = 4
$RuleProperties.Probe = $Probe
New-NetworkControllerLoadBalancerRule -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -Properties $RuleProperties -ResourceId "webserver1"
```

This example creates a new load balancing rule associated with load balancer resource lb1.

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
Specifies the load balancer resource where the load balancing rule belongs

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
Specifies the properties of the load balancing rule

```yaml
Type: LoadBalancingRuleProperties
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique identifier of the load balancing rule

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
Following properties of a load balancing rule can be added/changed:
- Front end IP configuration
- Back end address pool
- Protocol
- Front end port
- Health probe for the rule
- Load distribution
- Back End port
- Whether floating IP is enabled
- Idle timeout (in minutes)

## OUTPUTS

## NOTES

## RELATED LINKS

