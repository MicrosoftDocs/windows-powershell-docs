---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerlogicalsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLogicalSubnet
---

# New-NetworkControllerLogicalSubnet

## SYNOPSIS
Adds or updates a logical subnet in the Network Controller.

## SYNTAX

```
New-NetworkControllerLogicalSubnet [-LogicalNetworkId] <String> [-ResourceId] <String>
 [-Properties] <LogicalSubnetProperties> [[-ResourceMetadata] <ResourceMetadata>] [[-Etag] <String>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerLogicalSubnet** cmdlet adds a logical subnet to the Network Controller, or updates a logical subnet.
A logical subnet can exist only in a logical network.
For more information, see the **New-NetworkControllerLogicalNetwork** cmdlet.

## EXAMPLES

### Example 1: Create a logical subnet
```
PS C:\> $SubnetProperties = New-Object Microsoft.Windows.NetworkController.LogicalSubnetProperties
PS C:\> $SubnetProperties.AddressPrefix = "10.0.0.0/24"
PS C:\> $SubnetProperties.DefaultGateways = "10.0.0.1"
PS C:\> $SubnetProperties.DnsServers = "10.0.0.5"
PS C:\> $SubnetProperties.VlanId = "2"
PS C:\> $Route = New-Object Microsoft.Windows.NetworkController.FabricRouteProperties
PS C:\> $Route.Destination = "168.192.0.0/24"
PS C:\> $Route.nextHop = "10.0.0.10"
PS C:\> $SubnetProperties.routes = $Route
PS C:\> New-NetworkControllerLogicalSubnet -ConnectionUri "https://networkcontroller" -LogicalNetworkId "Network13" -Properties $SubnetProperties -ResourceId "Subnet01"
```

The first command creates a subnet properties object by using the **New-Object** cmdlet.
The command stores the result in the $SubnetProperties variable.

The next four commands assign values to properties of $SubnetProperties.

The sixth command creates a route properties object, and stores it in the $Route variable.

The next two commands assign values for the **Destination** and **nextHop** properties of $Route.

The tenth command assigns the value of $Route to the **routes** property of $SubnetProperties.

The final command creates a logical subnet in the logical network that has the resource ID Network13 on the Network Controller specified by a URI.
The command uses the properties of the subnet properties object in $SubnetProperties.
The new logical subnet has the resource ID Subnet01.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
This user must be present in the security group specified in the *ClientSecurityGroup* parameter in **Install-NetworkController**.

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
An ETag is an HTTP response header returned by an HTTP-compliant web server.
An ETag is used to determine change in the content of a resource.
The value of the header is an opaque string that represents the state of the resource when the response was generated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
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
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetworkId
Specifies the resource ID of the logical network to which this logical subnet belongs.

```yaml
Type: String
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
Specifies properties of a subnet that this cmdlet adds or updates.
You can specify the following properties:

- Address prefix of the subnet.
- VLAN ID of the subnet.
Valid values are the range from 0 through 4095.
- Routes that are contained in the logical subnet.
- IP address pools that are contained in the logical subnet.
- DNS servers that resolve DNS queries by devices or hosts connected to the logical subnet.
- Whether the subnet is a public subnet.
- One or more gateways for the subnet.

```yaml
Type: LogicalSubnetProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the logical subnet that this cmdlet adds or updates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceMetadata
Specifies metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Windows.NetworkController.LogicalSubnetProperties

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetworkControllerLogicalSubnet](./Get-NetworkControllerLogicalSubnet.md)

[Install-NetworkController](./Install-NetworkController.md)

[New-NetworkControllerLogicalNetwork](./New-NetworkControllerLogicalNetwork.md)

[Remove-NetworkControllerLogicalSubnet](./Remove-NetworkControllerLogicalSubnet.md)

[Set-NetworkController](./Set-NetworkController.md)

