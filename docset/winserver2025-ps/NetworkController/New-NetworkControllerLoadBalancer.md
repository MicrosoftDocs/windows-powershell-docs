---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerloadbalancer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLoadBalancer
---

# New-NetworkControllerLoadBalancer

## SYNOPSIS

This cmdlet adds/updates a load balancer resource.

## SYNTAX

```
New-NetworkControllerLoadBalancer [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <LoadBalancerProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The load balancer resource allows fine-grained configuration of how incoming traffic is distributed across VM instances in a virtual network.

It contains the following:

Front End IP configuration - This describes the exposed IP address of the load balancer.
For example, this address can be a reserved public or private IP address previously obtained by the customer, or an IP address dynamically allocated from a subnet of a virtual network.

BackEnd address pools - This describes the backend VMs behind the front end IP resource.

Load balancing rules - This defines how traffic that arrives at the front-end IP is to be sent to the backend IP

Health probe - Health probes are used by the load balancer to determine the health state of the backend pool members.

Inbound NAT rules - This can be used to forward external traffic to a specific VM in the virtual network

Outbound NAT rules - This can be used to forward VM network traffic from the virtual network to external destinations using network address translation (NAT).

## EXAMPLES

### Example 1

This example creates a public VIP for load balancing a pool of two VMs on a virtual network.
This also adds a HTTP health probe to detect whether one of the pool members becomes non-responsive.

```
//Prepare the load balancer object
$lbresourceId = "LB2"

$lbproperties = @{}
$lbproperties.frontendipconfigurations = @()
$lbproperties.backendAddressPools = @()
$lbproperties.probes = @()
$lbproperties.loadbalancingRules = @()
$lbproperties.OutboundNatRules = @()

//Assign front end IP
$vipip = "10.127.132.5"
$vipln = get-networkcontrollerlogicalnetwork -ConnectionUri $uri -resourceid "f8f67956-3906-4303-94c5-09cf91e7e311"

$fe = @{}
$fe.resourceId = "FE1"
$fe.resourceRef = "/loadBalancers/$lbresourceId/frontendIPConfigurations/$($fe.resourceId)"
$fe.properties = @{}
$fe.properties.subnet = @{}
$fe.properties.subnet.ResourceRef = $vipln.properties.Subnets[0].ResourceRef
$fe.properties.privateIPAddress = $vipip
$fe.properties.privateIPAllocationMethod = "Static"
$lbproperties.frontendipconfigurations += $fe

//Allocate backend address pool
$backend = @{}
$backend.resourceId = "BE1"
$backend.resourceRef = "/loadBalancers/$lbresourceId/backendAddressPools/$($b)"
$lbproperties.backendAddressPools += $backend

//Define health probe
$lbprobe = @{}
$lbprobe.ResourceId = "Probe1"
$lbprobe.resourceRef = "/loadBalancers/$lbresourceId/Probes/$($lbprobe.resourceId)"
$lbprobe.properties = @{}
$lbprobe.properties.protocol = "HTTP"
$lbprobe.properties.port = "80"
$lbprobe.properties.RequestPath = "/health.htm"
$lbprobe.properties.IntervalInSeconds = 5
$lbprobe.properties.NumberOfProbes = 11
$lbproperties.probes += $lbprobe

//Define load balancing rule
$lbrule = @{}
$lbrule.ResourceId = "webserver1"
$lbrule.properties = @{}
$lbrule.properties.FrontEndIPConfigurations = @()
$lbrule.properties.FrontEndIPConfigurations += $fe
$lbrule.properties.backendaddresspool = $backend
$lbrule.properties.protocol = "TCP"
$lbrule.properties.frontendPort = 80
$lbrule.properties.Probe = $lbprobe
$lbproperties.loadbalancingRules += $lbrule

//Add the load balancer to Network Controller
New-NetworkControllerLoadBalancer -ConnectionUri https://networkcontroller -ResourceId $lbresourceId -Properties $lbproperties
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

Following properties can be added/modified for a load balancer resource:

- Front end IP configuration
- Back end address pool
- Health probe
- Load balancing rule
- Outbound NAT rules
- Inbound NAT rules

```yaml
Type: LoadBalancerProperties
Parameter Sets: (All)
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId

Specifies the unique identifier of the load balancer resource

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

### Microsoft.Windows.NetworkController.LoadBalancerProperties

Following properties can be added/modified for a load balancer resource:

- Front end IP configuration
- Back end address pool
- Health probe
- Load balancing rule
- Outbound NAT rules
- Inbound NAT rules

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

