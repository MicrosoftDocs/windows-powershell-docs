---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollergatewaypool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerGatewayPool
---

# Get-NetworkControllerGatewayPool

## SYNOPSIS
Gets the configuration of one or more gateway pools.

## SYNTAX

```
Get-NetworkControllerGatewayPool [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerGatewayPool** cmdlet gets the configuration of the gateway pool specified by the *ResourceId* parameter.
If you do not specify the *ResourceId*, this cmdlet gets all gateway pools.

## EXAMPLES

### Example 1: Display all gateway pool configurations
```
PS C:\> Get-NetworkControllerGatewayPool -ConnectionUri "https://networkcontroller"
Tags             :
ResourceRef      : /GatewayPools/default
InstanceId       : 7a2ccc29-4bde-4f3f-a286-6678c0ed0c88
Etag             : W/"5da050d9-a31f-4d36-a0ff-009ff1cd54ad"
ResourceMetadata :
ResourceId       : default
Properties       : Microsoft.Windows.NetworkController.GatewayPoolProperties
Tags             :
ResourceRef      : /GatewayPools/GreGWPool
InstanceId       : 6974707a-f4d6-478e-8bf9-ed669c3e8717
Etag             : W/"7bcf66df-1000-4a85-9065-91faf09b1f42"
ResourceMetadata :
ResourceId       : GreGWPool
Properties       : Microsoft.Windows.NetworkController.GatewayPoolProperties
Tags             :
ResourceRef      : /GatewayPools/IPSecGWPool
InstanceId       : f51119ca-f3d7-4bdf-8289-9caaa1f5b824
Etag             : W/"daccaaae-d73f-4f08-8a69-cc88b0fad022"
ResourceMetadata :
ResourceId       : IPSecGWPool
Properties       : Microsoft.Windows.NetworkController.GatewayPoolProperties
```

This command gets all of the gateway pools configured with the Network Controller.

### Example 2: Display a specified gateway pool configuration
```
PS C:\> Get-NetworkControllerGatewayPool -ConnectionUri https://networkcontroller -ResourceId "IPSecGWPool"
Tags             :
ResourceRef      : /GatewayPools/IPSecGWPool
InstanceId       : f51119ca-f3d7-4bdf-8289-9caaa1f5b824
Etag             : W/"daccaaae-d73f-4f08-8a69-cc88b0fad022"
ResourceMetadata :
ResourceId       : IPSecGWPool
Properties       : Microsoft.Windows.NetworkController.GatewayPoolProperties
```

This command gets the gateway virtual machine configuration for IPSecGWPool.

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
Specifies an array of gateway pool resource IDs.

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

This cmdlet gets the following gateway pool parameters:

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a gateway pool):
  - Gateway pool type (for example, All, S2sIpSec, S2sGre).
  - Reference to the public IP addresses for IPSec connections.
  - Reference to the Generic Routing Encapsulation (GRE) VIP logical subnet.
  - Array of references to the gateway virtual machines in the pool.
  - Count of redundant gateway virtual machines.
  - Gateway virtual machine capacity in the pool.
  - Array of references to the virtual gateways configured in the pool.

## NOTES

## RELATED LINKS

[New-NetworkControllerGatewayPool](./New-NetworkControllerGatewayPool.md)

[Remove-NetworkControllerGatewayPool](./Remove-NetworkControllerGatewayPool.md)

