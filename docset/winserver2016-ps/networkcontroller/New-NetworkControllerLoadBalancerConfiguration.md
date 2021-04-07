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
online version: https://docs.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerloadbalancerconfiguration?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLoadBalancerConfiguration
---

# New-NetworkControllerLoadBalancerConfiguration

## SYNOPSIS
This cmdlet adds/updates the configuration of load balancer in Network Controller

## SYNTAX

```
New-NetworkControllerLoadBalancerConfiguration -ConnectionUri <Uri> -Properties <LoadBalancerManagerProperties>
 -ResourceId <string> [-CertificateThumbPrint <string>] [-Credential <PSCredential>] [-Etag <string>] [-Force]
 [-ResourceMetadata <ResourceMetadata>] [-Tags <psobject>]
```

## DESCRIPTION
This cmdlet adds/updates the configuration of load balancer in Network Controller.
This includes the virtual IP of load balancer service in Network Controller, different VIP pools associated with the load balancer and IP address ranges that are excluded from outbound NAT

## EXAMPLES

### Example 1

This example creates load balancer configuration in Network Controller, with REST endpoint as https://networkcontroller.
It specifies the load balancer service IP address and a VIP pool from an existing logical network and subnet.

```
\\Retrieve the VIP pool
$pool=Get-NetworkControllerIpPool -ConnectionUri https://networkcontroller -NetworkId ln1 -SubnetId subnet1

\\Create load balancer configuration object
$lbConfig = New-Object Microsoft.Windows.NetworkController.LoadBalancerManagerProperties
$lbconfig.loadBalancerManagerIpAddress = "10.0.0.23"
$lbconfig.VipPools = $pool

\\Add the load balancer configuration to Network Controller
New-NetworkControllerLoadBalancerConfiguration -ConnectionUri https://networkcontroller -ResourceId lbconfig1 -Properties $lbconfig
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

### -Properties
Specifies the properties of the load balancer configuration that can be changed:
1.
Load balancer manager virtual IP address (Load balancer manager is a service inside Network Controller)
2.
Virtual IP pools associated with the load balancer.
These should be existing IP pools as part of existing logical networks
3.
IP address ranges to be excluded from outbound NAT

```yaml
Type: LoadBalancerManagerProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique identifier for the load balancer configuration

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

### -Tags
@{Text=}

```yaml
Type: psobject
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
Following properties can be added/changed for a load balancer configuration:
1.
Load balancer manager virtual IP address (Load balancer manager is a service inside Network Controller)
2.
Virtual IP pools associated with the load balancer.
These should be existing IP pools as part of existing logical networks
3.
IP address ranges to be excluded from outbound NAT

## OUTPUTS

## NOTES
## RELATED LINKS

