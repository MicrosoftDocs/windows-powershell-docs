---
description: The Get-NetworkControllerVirtualNetworkPeering cmdlet gets a virtual network peering.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 09/27/2021
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollervirtualnetworkpeering?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVirtualNetworkPeering
---

# Get-NetworkControllerVirtualNetworkPeering

## SYNOPSIS
Gets a virtual network peering.

## SYNTAX

```
Get-NetworkControllerVirtualNetworkPeering [-VirtualNetworkId] <String[]> [[-ResourceId] <String[]>]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVirtualNetworkPeering** cmdlet gets a virtual network peering.
A peering enables connectivity between two virtual networks.

## EXAMPLES

### Example 1: Get a virtual network peering object
```powershell
Get-NetworkControllerVirtualNetworkPeering -VirtualNetworkId "Contoso_vnet1" -ConnectionUri https://networkcontroller
```

This example gets the virtual network peering object for the specified virtual network.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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
Specifies the Uniform Resource Identifier (URI) of a Network Controller.
The cmdlet gets the virtual network peering for that controller.


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

This user must be present in the security group provided in the **ClientSecurityGroup** parameter in the `Install-NetworkController` cmdlet.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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
Specifies the resource ID of the virtual network peering to get.

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

### -VirtualNetworkId
Specified the ID of a virtual network.
This cmdlet gets a peering for that network.

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

## NOTES

## RELATED LINKS

[New-NetworkControllerVirtualNetworkPeering](New-NetworkControllerVirtualNetworkPeering.md)

[Remove-NetworkControllerVirtualNetworkPeering](Remove-NetworkControllerVirtualNetworkPeering.md)
