---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerroute?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerRoute
---

# New-NetworkControllerRoute

## SYNOPSIS

This cmdlet adds a new route to the Network Controller

## SYNTAX

```
New-NetworkControllerRoute -ConnectionUri <Uri> -Properties <RouteProperties> -ResourceId <string>
 -RouteTableId <string> [-CertificateThumbPrint <string>] [-Credential <PSCredential>] [-Etag <string>]
 [-Force] [-ResourceMetadata <ResourceMetadata>]
```

## DESCRIPTION
This cmdlet adds a new route to the Network Controller.
This route is added to a route table.
If you want to route traffic to virtual appliances in your environment, you can specify routes and associate them to a virtual subnet.
Subnets rely on system routes until a route table is associated to the subnet.
After an association exists, routing is done based on Longest Prefix Match (LPM) among both user defined routes and system routes. 
If there is more than one route with the same LPM match, then the user defined route is selected first - before the system route.

## EXAMPLES

### Example 1

The above cmdlet adds a new route to a route table named Table1.
The next hop of this route is a virtual appliance.


```
$route = new-object Microsoft.Windows.NetworkController.Route
$route.properties = new-object Microsoft.Windows.NetworkController.RouteProperties
$route.properties.AddressPrefix = "0.0.0.0/0"
$route.properties.nextHopType = "VirtualAppliance"
$route.properties.nextHopIpAddress = "192.168.1.10"
New-NetworkControllerRoute -ConnectionUri https://networkcontroller -RouteTableId "Table1" -ResourceId "DefaultRoute" -Properties $route.properties
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
Following properties can be added/modified for a route:
a.
Address prefix
b.
Next hop type
c.
Next hop IP address

```yaml
Type: RouteProperties
Parameter Sets: (All)
Aliases: 
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique ID of the route

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

### -RouteTableId
Specifies the route table where the route is being added

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

## INPUTS

### 
Following properties can be added/modified for a route:
a.
Address prefix
b.
Next hop type
c.
Next hop IP address

## OUTPUTS

## NOTES

## RELATED LINKS

