---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollernetworkinterfaceipconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerNetworkInterfaceIpConfiguration
---

# Get-NetworkControllerNetworkInterfaceIpConfiguration

## SYNOPSIS
This cmdlet retrieves the IP configuration of a network interface from the Network Controller

## SYNTAX

```
Get-NetworkControllerNetworkInterfaceIpConfiguration [-NetworkInterfaceId] <String[]>
 [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves the IP configuration of a network interface from the Network Controller

## EXAMPLES

### Example 1

This example retrieves the all the IP configurations of a network interface named nw1, from the Network Controller
```
Get-NetworkControllerNetworkInterfaceIpConfiguration -ConnectionUri https://networkcontroller -NetworkInterfaceId nw1
```
## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies a user credential that has permission to perform this action.The default value is the current user.This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

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

### -NetworkInterfaceId
Specifies the network interface where the IP configuration belongs

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
Specifies the unique identifier for the resource

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

Following properties can be retrieved from an IP interface IP Configuration resource:
1. Private IP address
2. Private IP address allocation method
3. Load balancer backend address pools associated with the IP configuration
4. Load balancer inbound NAT Rules associated with the IP configuration
5. Subnet associated with the IP configuration
6. Public IP address associated with the IP configuration
7. Access control list associated with the IP Configuration
8. Service insertion rules associated with the IP configuration

## NOTES

## RELATED LINKS

