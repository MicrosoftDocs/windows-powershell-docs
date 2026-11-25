---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerloadbalancerinboundnatrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerLoadBalancerInboundNatRule
---

# Get-NetworkControllerLoadBalancerInboundNatRule

## SYNOPSIS
This cmdlet retrieves an inbound NAT rule associated with a load balancer resource.

## SYNTAX

```
Get-NetworkControllerLoadBalancerInboundNatRule [-LoadBalancerId] <String[]> [[-ResourceId] <String[]>]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves an inbound NAT rule associated with a load balancer resource. This can be used to forward external traffic to a specific VM in the virtual network

## EXAMPLES

### Example 1

This example retrieves an inbound NAT rule named InNat1 from a load balancer resource named lb1
```
Get-NetworkControllerLoadBalancerInboundNatRule -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId InNat1
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
Specifies the load balancer where the inbound NAT rule belongs

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
Specifies the unique identifier for the inbound NAT rule.

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

Following properties can be retrieved for an inbound NAT rule:
1. Front end port
2. Back end port
3. Whether floating IP is enabled
4. Idle timeout (in minutes)
5. Protocol
6. Back end IP addresses behind the NAT
7. Front end IP for the NAT

## NOTES

## RELATED LINKS

