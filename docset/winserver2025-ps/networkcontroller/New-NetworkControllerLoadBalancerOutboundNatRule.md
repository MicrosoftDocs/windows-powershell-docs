---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerloadbalanceroutboundnatrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLoadBalancerOutboundNatRule
---

# New-NetworkControllerLoadBalancerOutboundNatRule

## SYNOPSIS

Creates/modifies outbound NAT rules associated with a load balancer resource.

## SYNTAX

```
New-NetworkControllerLoadBalancerOutboundNatRule [-LoadBalancerId] <String> [-ResourceId] <String>
 [-Properties] <LoadBalancerOutboundNatRuleProperties> [[-ResourceMetadata] <ResourceMetadata>]
 [[-Etag] <String>] [-Force] -ConnectionUri <Uri> [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Creates/modifies outbound NAT rules associated with a load balancer resource.
This can be used to forward VM network traffic from the virtual network to external destinations using network address translation (NAT).

## EXAMPLES

### Example 1

This example creates a backend address pool from an existing network interface, and then creates a new outbound NAT rule with the backend address pool and an existing load balancer front end IP.
The outbound NAT rule is named outRule1 and it is associated with an existing load balancer resource named lb1

```
//Retrieve the backend IPs that will form the pool
$backEndIp=Get-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1

//Define the properties of the backend address pool
$bePool = New-Object Microsoft.Windows.NetworkController.LoadBalancerBackendAddressPoolProperties
$bePool.backEndIpConfiguration=$backEndIp

//Retrieve the load balancer frontend IP configured beforehand
$frontEndIp=Get-NetworkControllerLoadBalancerFrontendIpConfiguration -ConnectionUri https://networkcontroller -LoadBalancerId lb1

//create the backend address pool
$backEndIpPool=New-NetworkControllerLoadBalancerBackEndAddressPool -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId be1 -Properties $bePool

//create the outbound NAT rule
$outNat=New-Object Microsoft.Windows.NetworkController.LoadBalancerOutboundNatRuleProperties
$outNat.Protocol="TCP"
$outNat.BackEndAddressPool= $backEndIpPool
$outNat.frontEndIPConfigur
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerId
Specifies the load balancer resource where the outbound NAT rule belongs

```yaml
Type: string
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassInnerException
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

The thumbprint must be provided only if the network controller client authentication is X509 certificates.
**Get-NetworkController** retrieves that client authentication and authorization information.

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

### -Properties
Specifies the properties of the outbound NAT rule:
1.
Protocol
2.
Backend address pool associated with the NAT rule
3.
Front end IP associated with the NAT rule

```yaml
Type: LoadBalancerOutboundNatRuleProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique identifier for the outbound NAT rule

```yaml
Type: string
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Windows.NetworkController.LoadBalancerOutboundNatRuleProperties

Following properties of an outbound NAT rule can be added/changed:
1.
Protocol
2.
Backend address pool associated with the NAT rule
3.
Front end IP associated with the NAT rule

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

