---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerloadbalancer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerLoadBalancer
---

# Get-NetworkControllerLoadBalancer

## SYNOPSIS
This cmdlet retrieves the configuration of a load balancer resource from the Network Controller

## SYNTAX

```
Get-NetworkControllerLoadBalancer [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves the configuration of a load balancer resource. The load balancer resource allows fine-grained configuration of how incoming traffic is distributed across VM instances in a virtual network. It contains the following:
1. Front End IP configuration - This describes the exposed IP address of the load balancer. For example, this address can be a reserved public or private IP address previously obtained by the customer, or an IP address dynamically allocated from a subnet of a virtual network.
2. BackEnd address pools - This describes the backend VMs behind the front end IP resource.
3. Load balancing rules - This defines how traffic that arrives at the front-end IP is to be sent to the backend IP
4. Health probe - Health probes are used by the load balancer to determine the health state of the backend pool members.
5. Inbound NAT rules - This can be used to forward external traffic to a specific VM in the virtual network
6. Outbound NAT rules - This can be used to forward VM network traffic from the virtual network to external destinations using network address translation (NAT).

## EXAMPLES

### Example 1

This example retrieves the configuration of a load balancer resource named lb1 from the Network Controller
```
Get-NetworkControllerLoadBalancer -ConnectionUri https://networkcontroller -ResourceId lb1
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
Specifies the unique identifier for the load balancer resource.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

Following properties can be retrieved for a load balancer resource:
1. Front end IP configuration
2. Back end address pools
3. Load balancing rules
4. Inbound NAT rules
5. Outbound NAT rules
6. Health Probes
## NOTES

## RELATED LINKS

