---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerloadbalancerfrontendipconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerLoadBalancerFrontendIpConfiguration
---

# Get-NetworkControllerLoadBalancerFrontendIpConfiguration

## SYNOPSIS
This cmdlet retrieves the front end IP configuration of a load balancer resource from the Network Controller
## SYNTAX

```
Get-NetworkControllerLoadBalancerFrontendIpConfiguration [-LoadBalancerId] <String[]>
 [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves the front end IP configuration of a load balancer resource from the Network Controller. The front-end IP is commonly referred to as a Virtual IP (VIP). The VIP must be taken from an unused IP in one of the logical network IP Pool which has been previously given to the load balancer manager.
## EXAMPLES

### Example 1

This example retrieves all the front end IP resource associated with a load balancer resource named lb1

```
Get-NetworkControllerLoadBalancerFrontEndIpconfiguration -ConnectionUri https://networkcontroller -LoadBalancerId lb1
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

Required: True
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

### -LoadBalancerId
Specifies the load balancer where the resource belongs

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ResourceId
Specifies the unique identifier of the resource

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

Following properties can be retrieved for front end IP configuration of load balancer resource:
1. Private IP address (VIP)
2. Private IP address allocation method: Static or dynamic
3. Load balancing rules associated with the resource
4. Inbound NAT rules associated with the resource
5. Outbound NAT rules associated with the resource
6. Subnet associated with the resource
7. Access control list associated with the resource
8. Service insertion rules associated with the resource

## NOTES

## RELATED LINKS

