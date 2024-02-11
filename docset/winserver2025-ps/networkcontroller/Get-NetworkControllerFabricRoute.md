---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerfabricroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerFabricRoute
---

# Get-NetworkControllerFabricRoute

## SYNOPSIS
Gets the routes specified for logical subnet children of the logical network objects.

## SYNTAX

```
Get-NetworkControllerFabricRoute [-LogicalNetworkId] <String[]> [-SubnetId] <String[]>
 [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerFabricRoute** cmdlet gets the routes specified for logical subnet children of the logical network objects.
If you specify a route to get, this cmdlet gets the destination and next hop of the route.
If you do not specify a route, this cmdlet returns all the routes in the logical subnet.

## EXAMPLES

### Example 1: Display all routes for a subnet
```
PS C:\> Get-NetworkControllerFabricRoute -ConnectionUri "https://networkcontroller" -LogicalNetworkId "Network13" -SubnetId "Subnet01"
```

This command retrieves all the routes in the subnet Subnet01.
That subnet is in a logical network called Network13.

### Example 2: Display address and next hop
```
PS C:\> $Route = Get-NetworkControllerFabricRoute -ConnectionUri "https://networkcontroller" -LogicalNetworkId "Network13" -SubnetId "Subnet01" -ResourceId "Route21"
PS C:\> $Route.Properties
```

The first command gets a route that has the ID Route21 in the subnet that has the ID Subnet01.
That subnet is in the logical network Network13.
The command stores the route in the $Route variable.

The second command displays properties of the route stored in $Route.
Specifically, it shows the destination address and the next hop address.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint of a digital public key X.509 certificate of a user account that has permission to perform this action.
In order for Network Controller to authorize the account, specify this thumbprint by using the *ClientCertificateThumbprint* parameter of the **Install-NetworkController** or **Set-NetworkController** cmdlet.

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
Specifies the Uniform Resource Identifier (URI) of the Network Controller.
All Representational State Transfer (REST) clients use this URI to connect to Network Controller.

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
The default value is the current user.
This user must be present in the security group specified in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

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

### -LogicalNetworkId
Specifies an array of IDs of logical networks from which this cmdlet gets routes.

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
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies the resource ID of the route that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Specifies an array of IDs of subnets from which this cmdlet gets routes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

This cmdlet returns an object that contains the destination and the next hop for a particular network route.

## NOTES

## RELATED LINKS

[Install-NetworkController](./Install-NetworkController.md)

[New-NetworkControllerFabricRoute](./New-NetworkControllerFabricRoute.md)

[Remove-NetworkControllerFabricRoute](./Remove-NetworkControllerFabricRoute.md)

[Set-NetworkController](./Set-NetworkController.md)

