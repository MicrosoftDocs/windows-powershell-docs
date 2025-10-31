---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollergateway?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerGateway
---

# Get-NetworkControllerGateway

## SYNOPSIS
Gets the configuration of one or more gateway virtual machines.

## SYNTAX

```
Get-NetworkControllerGateway [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerGateway** cmdlet gets the configuration of the gateway virtual machines specified by the *ResourceId* parameter.
If you do not specify a *ResourceId*, this cmdlet gets the configuration of all gateway virtual machines.

## EXAMPLES

### Example 1: Display all gateway virtual machine configurations
```
PS C:\> Get-NetworkControllerGateway -ConnectionUri "https://networkcontroller"
Tags             :
ResourceRef      : /Gateways/MTGW01
InstanceId       : 6b77e9b1-8a08-4a5e-8c0a-ef07785efc7b
Etag             : W/"db8d83eb-9a14-4af8-a000-f0c74ac4957f"
ResourceMetadata :
ResourceId       : MTGW01
Properties       : Microsoft.Windows.NetworkController.GatewayProperties
Tags             :
ResourceRef      : /Gateways/MTGW02
InstanceId       : 72451c9e-82e8-40e4-b426-1186ca1fae6f
Etag             : W/"c3eccdc9-08a2-4557-a8d0-cbbfc03349ce"
ResourceMetadata :
ResourceId       : MTGW02
Properties       : Microsoft.Windows.NetworkController.GatewayProperties
```

This command gets all gateway virtual machines configured with the Network Controller.

### Example 2: Display the configuration for a specified gateway virtual machine
```
PS C:\> Get-NetworkControllerGateway -ConnectionUri https://networkcontroller -ResourceId "MTGW01"
Tags             :
ResourceRef      : /Gateways/MTGW01
InstanceId       : 6b77e9b1-8a08-4a5e-8c0a-ef07785efc7b
Etag             : W/"db8d83eb-9a14-4af8-a000-f0c74ac4957f"
ResourceMetadata :
ResourceId       : MTGW01
Properties       : Microsoft.Windows.NetworkController.GatewayProperties
```

This command gets the gateway virtual machine configuration for MTGW01.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.

This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies a user credential that has permission to perform this action.
The default value is the current user.
This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

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
This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies an array of resource IDs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

This cmdlet returns one or more objects that contain the following fields:


- Resource reference URI
- Created time of the resource
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a gateway virtual machine):
  - Gateway virtual machine type.
  - Health state.
  - Gateway virtual machine role/state (active/redundant).
  - Total capacity.
  - Available capacity.
  - Array of external source IP addresses.
  - Reference to the corresponding virtual server.
  - References to the associated internal and external network interfaces.
  - Reference to the corresponding gateway pool.
  - Array of references to the virtual gateways configured on the gateway virtual machine.
  - PA space Border Gateway Protocol (BGP) configuration of the gateway virtual machine.
  - Array of connections.

## NOTES

## RELATED LINKS

[New-NetworkControllerGateway](./New-NetworkControllerGateway.md)

[Remove-NetworkControllerGateway](./Remove-NetworkControllerGateway.md)

