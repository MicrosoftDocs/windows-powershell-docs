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
title: Get-NetworkControllerStatistics
ms.reviewer:
ms.assetid: 4D06BF6F-B920-496E-BA38-D14EB91CB372
---

# Get-NetworkControllerStatistics

## SYNOPSIS
This cmdlet displays health and usage statistics of resources in Network Controller

## SYNTAX

```
Get-NetworkControllerStatistics [-ConnectionUri <Uri>] [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet displays health and usage statistics of resources in Network Controller. You can view the count of total resources, healthy resources, unhealthy resources and resources with unknown health for virtual network, gateway and load balancer resources. You can also see the utilization of public IPs, backend IPs and MAC address pools.

## EXAMPLES

### Example 1

This example displays the health statistics of resources in Network Controller
```
$stats=Get-NetworkControllerStatistics -ConnectionUri https://networkcontroller
$stats.Properties.HealthStatistics
```

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.The default value is the current user.This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### 

Following properties are displayed by the cmdlet:

Resource health (for virtual networks, Gateways and Load balancers) 
1. Count of total resources 
2. Count of healthy resources 
3. Count of unhealthy resources 
4. Count of resources in warning state 
5. Count of resources with unknown health state

Usage statistics 
1. Public IP utilization - Total resource count and count of resources in use 
2. Backend IP utilization - Total resource count and count of resources in use 
3. MAC pool utilization - Total resource count and count of resources in use

## NOTES

## RELATED LINKS

