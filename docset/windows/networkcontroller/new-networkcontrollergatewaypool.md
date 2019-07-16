---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-NetworkControllerGatewayPool
ms.reviewer:
ms.assetid: 140778A1-B623-4524-9313-A67C8C010AFE
---

# New-NetworkControllerGatewayPool

## SYNOPSIS
Creates a gateway pool.

## SYNTAX

```
New-NetworkControllerGatewayPool [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <GatewayPoolProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerGatewayPool** cmdlet adds a new gateway pool configuration to the Network Controller.
If the specified gateway pool configuration already exists with Network Controller, this cmdlet overwrites and replaces the older configuration.

## EXAMPLES

### Example 1: Add a gateway pool configuration to the Network Controller
```
PS C:\> New-NetworkControllerGatewayPool -ConnectionUri "https://networkcontroller"
-ResourceId "GreGWPool" -Properties $greGwPoolProperties
Confirm
Performing the operation 'New-NetworkControllerGatewayPool' on entities of type 'Microsoft.Windows.NetworkController.GatewayPool' via 'https://networkcontroller/networking/v1/gatewaypools/GreGWPool'. Are you sure you want to continue? 
 [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): yes

Tags             : 
ResourceRef      : /GatewayPools/GreGWPool
InstanceId       : 6974707a-f4d6-478e-8bf9-ed669c3e8717
Etag             : W/"7bcf66df-1000-4a85-9065-91faf09b1f42"
ResourceMetadata : 
ResourceId       : GreGWPool
Properties       : Microsoft.Windows.NetworkController.GatewayPoolProperties
```

This command adds a new gateway pool configuration to Network Controller.

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

### -Etag
Specifies the entity tag (ETag) of the resource.
An ETag is an HTTP response header returned by an HTTP-compliant web server.
An ETag is used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

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

### -Properties
Specifies properties for the gateway pool.

```yaml
Type: GatewayPoolProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Species the resource ID of a gateway pool.

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
This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet outputs the following information: 

- Resource reference URI.
- Created time of the resource.
- Instance ID of the resource.
- Resource metadata.
- Properties of the resource: 
"{

         ""IPConfiguration"" : {

                  ""GREVipSubnets"": @( @{""ResourceRef"": ""\<string\>""} ), 

                  ""PublicIPAddresses"": @( @{""ResourceRef"": ""\<string\>""} ), 

          },

         ""RedundantGatewayCount"" : \<Uint32\>,

         ""GatewayCapacityKiloBitsPerSecond"": \<Uint32\>

}"

## NOTES

## RELATED LINKS

[Get-NetworkControllerGatewayPool](./Get-NetworkControllerGatewayPool.md)

[Remove-NetworkControllerGatewayPool](./Remove-NetworkControllerGatewayPool.md)

