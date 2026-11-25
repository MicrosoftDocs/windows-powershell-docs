---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerlogicalsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerLogicalSubnet
---

# Get-NetworkControllerLogicalSubnet

## SYNOPSIS
Gets settings of a logical subnet in the Network Controller.

## SYNTAX

```
Get-NetworkControllerLogicalSubnet [-LogicalNetworkId] <String[]> [[-ResourceId] <String[]>]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerLogicalSubnet** cmdlet gets settings of a logical subnet in the Network Controller.
A logical subnet comprises one or more subnet/VLAN pairs.
VLAN is required.
If a subnet is not associated with a VLAN, VLAN takes a value of zero (0).

## EXAMPLES

### Example 1: Get settings for a logical subnet
```
PS C:\> Get-NetworkControllerLogicalSubnet -ConnectionUri "https://networkcontroller" -LogicalNetworkId "Network13" -ResourceId "Subnet01"
```

This command retrieves settings for a logical subnet that has the resource ID Subnet01.
The subnet belongs to the logical network that has the resource ID Network13.
The Network Controller is specified by the connection URI.

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

### -LogicalNetworkId
Specifies the resource ID of the logical network from which this cmdlet gets subnets.

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

### -ResourceId
Specifies an array of resources that this cmdlet retrieves.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

This cmdlet returns an object that contains the following settings:

- Address prefix of the subnet.
- VLAN ID of the subnet.
Valid values are the range from 0 through 4095.
- Routes that are contained in the logical subnet.
- IP address pools that are contained in the logical subnet.
- DNS servers that devices or hosts use to resolve DNS queries connected to the logical subnet.
- Reference to network interfaces that are attached to this logical subnet.
- Whether this subnet is a public subnet.
- One or more gateways for the subnet.

## NOTES

## RELATED LINKS

[New-NetworkControllerLogicalSubnet](./New-NetworkControllerLogicalSubnet.md)

[Remove-NetworkControllerLogicalSubnet](./Remove-NetworkControllerLogicalSubnet.md)

[Install-NetworkController](./Install-NetworkController.md)

[Set-NetworkController](./Set-NetworkController.md)

