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
online version: https://docs.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerloadbalancermux?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLoadBalancerMux
---

# New-NetworkControllerLoadBalancerMux

## SYNOPSIS

This cmdlet adds/updates the configuration of a load balancer VM managed by the Network Controller.

## SYNTAX

```
New-NetworkControllerLoadBalancerMux -ConnectionUri <Uri> -ResourceId <string>
 [-CertificateThumbPrint <string>] [-Credential <PSCredential>] [-Etag <string>] [-Force]
 [-Properties <LoadBalancerMuxProperties>] [-ResourceMetadata <ResourceMetadata>] [-Tags <psobject>]
```

## DESCRIPTION
This cmdlet adds/updates the configuration of a load balancer VM managed by the Network Controller.
Multiple load balancer VMs can be deployed to load balance traffic to virtual machines in the virtual network

## EXAMPLES

### Example 1

This example adds a new load balancer MUX named Mux1 to the Network Controller.
The MUX configuration includes a connection resource to connect to the MUX, local ASN of the MUX and the BGP peer configuration for the MUX.

```
$peer=New-Object Microsoft.Windows.NetworkController.PeerRouterConfiguration
$peer.LocalIpAddress="10.0.0.1"
$peer.RouterName="Peer1"
$peer.RouterIpAddress="10.0.0.5"
$peer.peerASN=12345
$peer.Id="peer1"
$routerConfig=New-Object Microsoft.Windows.NetworkController.RouterConfiguration
$routerConfig.LocalAsn=12344
$routerConfig.PeerRouterConfigurations=$peer

$credentialProperties = [Microsoft.Windows.NetworkController.CredentialProperties]@{Type="UsernamePassword";UserName="admin";Value="password"}
New-NetworkControllerCredential -ResourceId cred1 -ConnectionUri https://networkcontroller -Properties $credentialProperties
$credential= Get-NetworkControllerCredential -ResourceId cred1 -ConnectionUri https://networkcontroller

$muxproperties=New-Object Microsoft.Windows.NetworkController.LoadBalancerMuxProperties
$muxproperties.Connections = @([Microsoft.Windows.NetworkController.Connection]@{ManagementAddresses=@("192.168.0.12");Credential=$credential})
$muxproperties.Rout
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
Following properties can be added/updated for a load balancer MUX:
1.
Router configuration - This includes local ASN of the MUX router and peer router configuration (Name, local IP address, peer IP address, Peer ASN)
2.
Certificate of the MUX
3.
An array of connections that specifies the information needed to connect to the MUX for the purposes of managing and controlling the device.

```yaml
Type: LoadBalancerMuxProperties
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the ID of the MUX resource

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
Following properties can be added/updated for a load balancer MUX:
1.
Router configuration - This includes local ASN of the MUX router and peer router configuration (Name, local IP address, peer IP address, Peer ASN)
2.
Certificate of the MUX
3.
An array of connections that specifies the information needed to connect to the MUX for the purposes of managing and controlling the device.

## OUTPUTS

## NOTES
## RELATED LINKS

