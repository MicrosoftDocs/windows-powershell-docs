---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
manager: jasgro
Module Name: NetworkController
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerloadbalancerprobe?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLoadBalancerProbe
---

# New-NetworkControllerLoadBalancerProbe

## SYNOPSIS

This cmdlet adds/updates the health probes associated with a load balancer.

## SYNTAX

```
New-NetworkControllerLoadBalancerProbe -ConnectionUri <Uri> -LoadBalancerId <string>
 -Properties <LoadBalancerProbeProperties> -ResourceId <string> [-CertificateThumbPrint <string>]
 [-Credential <PSCredential>] [-Etag <string>] [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds/updates the health probes associated with a load balancer.
Health probes are used by the load balancer to determine the health state of the backend pool members.

## EXAMPLES

### Example 1

This example creates a new health probe named probe1 for a load balancer resource named lb1.
This is a HTTP probe that queries to the RequestPath of "/health.htm".
The query is performed every 5 seconds, as specified by the IntervalInSeconds property.
The health probe must receive an HTTP response code of 200 for 8 consecutive queries for the probe to consider the backend IP to be healthy.
If the backend IP is not healthy, the load balancer will not send traffic to the IP.


```
$probe=New-Object Microsoft.Windows.NetworkController.LoadBalancerProbeProperties
$probe.protocol="HTTP"
$probe.port="80"
$probe.RequestPath="/health.htm"
$probe.IntervalInSeconds=5
$probe.NumberofProbes=8
New-NetworkControllerLoadBalancerProbe -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId Probe1 -Properties $probe
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
Specifies the load balancer where the health probe belongs

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
Following properties can be added/changed for a load balancer probe:
- Protocol
- Port
- Request path that has to be probed
- Probe interval (in seconds)
- Number of retries after which a backend resource is deemed unhealthy

```yaml
Type: LoadBalancerProbeProperties
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique ID of the health probe rule

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
Following properties can be added/changed for a load balancer probe:
- Protocol
- Port
- Request path that has to be probed
- Probe interval (in seconds)
- Number of retries after which a backend resource is deemed unhealthy

## OUTPUTS

## NOTES

## RELATED LINKS

