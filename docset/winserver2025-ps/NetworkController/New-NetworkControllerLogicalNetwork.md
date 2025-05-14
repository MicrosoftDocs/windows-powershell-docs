---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerlogicalnetwork?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerLogicalNetwork
---

# New-NetworkControllerLogicalNetwork

## SYNOPSIS
Adds or updates a logical network in Network Controller.

## SYNTAX

```
New-NetworkControllerLogicalNetwork [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <LogicalNetworkProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerLogicalNetwork** cmdlet adds a logical network to the Network Controller, or updates an existing logical network.
A logical network represents a logical partition of a physical network that is dedicated for a particular purpose.
A logical network is a collection of logical subnets.

## EXAMPLES

### Example 1: Create a logical network that has network virtualization disabled
```
PS C:\> $NetworkProperties = New-Object Microsoft.Windows.NetworkController.LogicalNetworkProperties
PS C:\> $NetworkProperties.NetworkVirtualizationEnabled = $False
PS C:\> New-NetworkControllerLogicalNetwork -ConnectionUri "https://networkcontroller" -ResourceId "Network13" -Properties $NetworkProperties
```

The first command creates a **LogicalNetworkProperties** object by using the **New-Object** cmdlet.
The command stores the object in the $NetworkProperties variable.

The second command assigns a value of $False to the **NetworkVirtualizationEnabled** property of $NetworkProperties.

The final command creates a logical network that has the resource ID logicalnw1 in the Network Controller.
Because $NetworkProperties has a value of $False for **NetworkVirtualizationEnabled**, network virtualization is disabled in this network.

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
Position: 5
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
Specifies properties of a logical network that can be added or updated.
You can update the list of subnets this is contained in the logical network and whether network virtualization is enabled for the logical network.

```yaml
Type: LogicalNetworkProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the ID of the logical network that this cmdlet adds to the Network Controller.

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

### -ResourceMetadata
Specifies metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags


```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### Microsoft.Windows.NetworkController.LogicalNetworkProperties

This cmdlet accepts a **LogicalNetworkProperties** object that can contain the following properties:

- The subnets for the logical network
- Whether network virtualization is enabled for the logical network.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetworkControllerLogicalNetwork](./Get-NetworkControllerLogicalNetwork.md)

[Install-NetworkController](./Install-NetworkController.md)

[Remove-NetworkControllerLogicalNetwork](./Remove-NetworkControllerLogicalNetwork.md)

[Set-NetworkController](./Set-NetworkController.md)

