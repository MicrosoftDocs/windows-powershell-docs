---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollervirtualgatewaypolicymap?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVirtualGatewayPolicyMap
---

# Get-NetworkControllerVirtualGatewayPolicyMap

## SYNOPSIS
Gets a BGP routing policy map.

## SYNTAX

```
Get-NetworkControllerVirtualGatewayPolicyMap [-VirtualGatewayId] <String[]> [[-ResourceId] <String[]>]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerVirtualGatewayPolicyMap** cmdlet gets the configuration of one or more Border Gateway Protocol (BGP) routing policy map(s) for a tenant.

Use the *ResourceId* parameter to specify the policy map to get.
If you do not specify a *ResourceId*, this cmdlet gets all policy maps corresponding to a tenant.

## EXAMPLES

### Example 1: Display all policy map configurations for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayPolicyMap -ConnectionUri "https://networkcontroller" -VirtualGatewayId "Contoso"
```

This command retrieves all the policy maps for the virtual gateway Contoso configured with the Network Controller.

### Example 2: Display a specified policy map configuration for the tenant virtual gateway
```
PS C:\> Get-NetworkControllerVirtualGatewayPolicyMap -ConnectionUri "https://networkcontroller" -VirtualGatewayId "Contoso" -ResourceId "Ingress"
```

This command retrieves the Ingress policy map configuration for the tenant Contoso.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies an array of resource IDs.

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

### -VirtualGatewayId
Specifies an array of virtual gateway IDs.

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

This cmdlet returns object(s) that contain the following fields:

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Resource ID.
- Properties of the resource (a virtual/tenant gateway's BGP router):
  - Provisioning state.
  - List of policy map entries.
Each entry has the policy type, list of match criteria, and list of set actions.
- List of resource references to the BGP peers that have this policy map applied in ingress.
- List of resource references to the BGP peers that have this policy map applied in egress.

## NOTES

## RELATED LINKS

[New-NetworkControllerVirtualGatewayPolicyMap](./New-NetworkControllerVirtualGatewayPolicyMap.md)

[Remove-NetworkControllerVirtualGatewayPolicyMap](./Remove-NetworkControllerVirtualGatewayPolicyMap.md)

