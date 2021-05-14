---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerpublicipaddress?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerPublicIpAddress
---

# New-NetworkControllerPublicIpAddress

## SYNOPSIS

This cmdlet adds/updates a public IP address resource in the Network Controller.

## SYNTAX

```
New-NetworkControllerPublicIpAddress -ConnectionUri <Uri> -Properties <PublicIpAddressProperties>
 -ResourceId <string> [-CertificateThumbPrint <string>] [-Credential <PSCredential>] [-Etag <string>] [-Force]
 [-ResourceMetadata <ResourceMetadata>] [-Tags <psobject>]
```

## DESCRIPTION
This cmdlet adds/updates a public IP address resource in the Network Controller.
This publicIpAddress resource is used by the virtualGateway resource and the loadBalancer resource to indicate the IP Address that can be used to communicate with the virtual network from outside it.

## EXAMPLES

### Example 1

This example creates a public IP address resource named PublicIP1 in the NetworkController.
The IP address associated with this resource is 0.124.231.21 and the IP address allocation method is static.

```
$IpAddress=New-Object Microsoft.Windows.NetworkController.PublicIpAddressProperties
$IpAddress.IPAddress="10.124.231.21"
$IpAddress.PublicIpAllocationMethod="Static"
New-NetworkControllerPublicIpAddress -ConnectionUri https://networkcontroller -ResourceId PublicIp1 -Properties $IpAddress
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
Following properties can be added/updated for the publicIPAddress resource:
1.
Public IP address of the resource
2.
IP allocation method: Static or dynamic
3.
TCP idle timeout in minutes

```yaml
Type: PublicIpAddressProperties
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique ID of the IP Address resource

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
Following properties can be added/updated for the publicIPAddress resource:
1.
Public IP address of the resource
2.
IP allocation method: Static or dynamic
3.
TCP idle timeout in minutes

## OUTPUTS

## NOTES

## RELATED LINKS

