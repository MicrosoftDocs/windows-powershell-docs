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
title: Get-NetworkControllerLoadBalancerConfiguration
ms.reviewer:
ms.assetid: 9A4BA797-325C-47D7-8298-28D1982D0853
---

# Get-NetworkControllerLoadBalancerConfiguration

## SYNOPSIS
Retrieves the configuration of the load balancer from the Network Controller

## SYNTAX

```
Get-NetworkControllerLoadBalancerConfiguration [-ConnectionUri <Uri>] [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION

Retrieves the configuration of the load balancer from the Network Controller. This includes the load balancing service virtual IP (VIP) and the different VIP pools associated with the load balancer.

## EXAMPLES

### Example 1

This example retrieves the load balancer configuration from Network Controller. In this example, The Network Controller is hosted at https://networkcontroller.

```
Get-NetworkControllerLoadBalancerConfiguration -ConnectionUri https://networkcontroller
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### 

Following properties can be retrieved for a load balancer configuration:

- Load balancer manager virtual IP address (Load balancer manager is a service inside Network Controller)
- Virtual IP pools associated with the load balancer. These should be existing IP pools as part of existing logical networks
- IP address ranges to be excluded from outbound NAT

## NOTES

## RELATED LINKS

