---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerserverinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerServerInterface
---

# Get-NetworkControllerServerInterface

## SYNOPSIS
Gets settings of physical network interfaces from the Network Controller.

## SYNTAX

```
Get-NetworkControllerServerInterface [-ServerId] <String[]> [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerServerInterface** cmdlet gets settings of physical network interfaces from the Network Controller.

## EXAMPLES

### Example 1: Get settings of a network interface
```
PS C:\> Get-NetworkControllerServerInterface -ConnectionUri "https://networkcontroller" -ServerId "Server01" -ResourceId "Interface01"
```

This command retrieves settings of a network interface that has the resource ID Interface01.
The interface is on a server that has the resource ID Server01.
The URI identifies the Network Controller.

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
Specifies an array of resource IDs of server interfaces for which this cmdlet gets settings.

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

### -ServerId
Specifies the server from which this cmdlet gets settings for an interface.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

This cmdlet returns an object that contains the following properties:

- Administrative status of the interface.
Valid values are Up and Down.
- Interface index.
- Interface name.
- Interface speed.
- IP configuration of the interface.
This property contains IP address, network prefix, default gateway, VLANs, and whether the IP has been obtained over DHCP.
- Logical subnets to which the network interface is connected.
- MAC address.
- Operational status of the interface.
- VLAN IDs of networks to which the interface is connected.
- Whether this interface is a baseboard management controller (BMC) interface.

## NOTES

## RELATED LINKS

[Install-NetworkController](./Install-NetworkController.md)

[New-NetworkControllerServerInterface](./New-NetworkControllerServerInterface.md)

[Remove-NetworkControllerServerInterface](./Remove-NetworkControllerServerInterface.md)

[Set-NetworkController](./Set-NetworkController.md)

