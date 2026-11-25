---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerroutetable?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerRouteTable
---

# New-NetworkControllerRouteTable

## SYNOPSIS

This cmdlet creates a new route table in the Network Controller

## SYNTAX

```
New-NetworkControllerRouteTable [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <RouteTableProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new route table in the Network Controller.
If you want to route traffic to virtual appliances in your environment, you can specify routes and associate them to a virtual subnet.
Subnets rely on system routes until a route table is associated to the subnet.
After an association exists, routing is done based on Longest Prefix Match (LPM) among both user defined routes and system routes.
If there is more than one route with the same LPM match, then the user defined route is selected first - before the system route.

## EXAMPLES

### Example 1
```
$route = new-object Microsoft.Windows.NetworkController.Route
$route.ResourceID = "0_0_0_0_0"
$route.properties = new-object Microsoft.Windows.NetworkController.RouteProperties
$route.properties.AddressPrefix = "0.0.0.0/0"
$route.properties.nextHopType = "VirtualAppliance"
$route.properties.nextHopIpAddress = "192.168.1.10"
$routetableproperties.routes += $route
New-NetworkControllerRouteTable -ConnectionUri https://networkcontroller -ResourceId "Route1" -Properties $routetableproperties
```

Description



The above cmdlet creates a route table named Route1 with a single route named "0_0_0_0_0"

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
Each route table can have multiple routes.
Each route has the following properties:
1.
Address prefix
2.
Next hop type
3.
Next hop IP address

```yaml
Type: RouteTableProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the ID of the route table to be created

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

### Microsoft.Windows.NetworkController.RouteTableProperties

Each route table can have multiple routes.
Each route has the following properties:
1.
Address prefix
2.
Next hop type
3.
Next hop IP address

## OUTPUTS

### System.Object

## NOTES
## RELATED LINKS

