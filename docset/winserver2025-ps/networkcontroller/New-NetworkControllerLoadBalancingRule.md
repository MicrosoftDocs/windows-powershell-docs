---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerloadbalancingrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLoadBalancingRule
---

# New-NetworkControllerLoadBalancingRule

## SYNOPSIS

This cmdlet adds/updates a load balancing rule associated with a load balancer.

## SYNTAX

```
New-NetworkControllerLoadBalancingRule [-LoadBalancerId] <String> [-ResourceId] <String>
 [-Properties] <LoadBalancingRuleProperties> [[-ResourceMetadata] <ResourceMetadata>] [[-Etag] <String>]
 [-Force] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet adds/updates a load balancing rule associated with a load balancer.
This load balancing rule defines how traffic that arrives at the front-end IP is to be sent to the backend IP

## EXAMPLES

### Example 1 - define a load balancing rule

```powershell
PS C:\> Import-Module NetworkController
# Frontend
# Create the front end IP resource
PS C:\> $frontEndIp = New-Object Microsoft.Windows.NetworkController.LoadBalancerFrontEndIpConfigurationProperties
PS C:\> $frontEndIp.PrivateIpAddress="10.127.32.12"
PS C:\> $frontEndIp.PrivateIPAllocationMethod="Static"

PS C:\> $FrontEndIPConfig = New-NetworkControllerLoadBalancerFrontEndIpConfiguration -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId frontEnd1 -Properties $frontEndIp

# Backend
# Retrieve the backend IPs that will form the pool
PS C:\> $backEndIp = Get-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1

## Define the properties of the backend address pool
PS C:\> $bePool = New-Object Microsoft.Windows.NetworkController.LoadBalancerBackendAddressPoolProperties
PS C:\> $bePool.BackendIPConfigurations = $backEndIp

PS C:\> $BackEndAddressPool = New-NetworkControllerLoadBalancerBackEndAddressPool -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId be1 -Properties $bePool

# Probe
PS C:\> $ProbeProperties = New-Object Microsoft.Windows.NetworkController.LoadBalancerProbeProperties
PS C:\> $ProbeProperties.protocol="HTTP"
PS C:\> $ProbeProperties.port="80"
PS C:\> $ProbeProperties.RequestPath="/health.htm"
PS C:\> $ProbeProperties.IntervalInSeconds=5
PS C:\> $ProbeProperties.NumberofProbes=8
PS C:\> $Probe = New-NetworkControllerLoadBalancerProbe -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -ResourceId Probe1 -Properties $ProbeProperties

# Rule properties
PS C:\> $RuleProperties = New-Object Microsoft.Windows.NetworkController.LoadBalancingRuleProperties
PS C:\> $RuleProperties.FrontEndIPConfigurations += $FrontEndIPConfig
PS C:\> $RuleProperties.BackendAddressPool = $BackEndAddressPool
PS C:\> $RuleProperties.protocol = "TCP"
PS C:\> $RuleProperties.FrontEndPort = 80
PS C:\> $RuleProperties.BackEndPort = 80
PS C:\> $RuleProperties.IdleTimeoutInMinutes = 4
PS C:\> $RuleProperties.Probe = $Probe
PS C:\> New-NetworkControllerLoadBalancingRule -ConnectionUri https://networkcontroller -LoadBalancerId lb1 -Properties $RuleProperties -ResourceId "webserver1"
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
Specifies the load balancer resource where the load balancing rule belongs

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
Specifies the properties of the load balancing rule

```yaml
Type: LoadBalancingRuleProperties
Parameter Sets: (All)
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Windows.NetworkController.LoadBalancingRuleProperties

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

### System.Object

## NOTES

## RELATED LINKS

