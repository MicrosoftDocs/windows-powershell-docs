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
title: New-NetworkControllerGateway
ms.reviewer:
ms.assetid: 57A2F1F6-D366-4203-BD26-04E9C20FDDB3
---

# New-NetworkControllerGateway

## SYNOPSIS
Creates a gateway virtual machine.

## SYNTAX

```
New-NetworkControllerGateway [-ResourceId] <String> [[-Tags] <PSObject>] [-Properties] <GatewayProperties>
 [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerGateway** cmdlet adds a new gateway virtual machine configuration to the Network Controller.
If the specified gateway virtual machine configuration already exists with Network Controller, this cmdlet overwrites and replaces the older configuration.

## EXAMPLES

### Example 1: Add a new gateway virtual machine configuration to the Network Controller
```
PS C:\> New-NetworkControllerGateway -ConnectionUri https://networkcontroller -ResourceId "MTGW03" -Properties $mtgw03.Properties
Confirm
Performing the operation 'New-NetworkControllerGateway' on entities of type 'Microsoft.Windows.NetworkController.Gateway' via 'https://networkcontroller/networking/v1/gateways/MTGW03'. Are you sure you
want to continue? 
 [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): yes



Tags             : 
ResourceRef      : /Gateways/MTGW03
InstanceId       : a856b20b-0009-4515-9d86-9a17cbda0733
Etag             : W/"0383c1c2-b0b3-420b-8105-05ef854c1f7c"
ResourceMetadata : 
ResourceId       : MTGW03
Properties       : Microsoft.Windows.NetworkController.GatewayProperties
```

This command adds a new gateway virtual machine configuration to the Network Controller.

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
Specifies properties for the gateway virtual machine.

```yaml
Type: GatewayProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Species the resource ID of a gateway virtual machine.

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
- Resource ID.
- Properties of the resource: 
"{
    ""VirtualServer"" : @{ ""ResourceRef"": ""\<string\>"" },
    ""NetworkInterfaces"": @{
        ""ExternalNetworkInterface"": @{ ""ResourceRef"": ""\<string\>"" },
        ""InternalNetworkInterface"": @{ ""ResourceRef"": ""\<string\>"" }
    },
    ""BgpConfig"": @{
        ""ExtASNumber"": """",
        ""BgpPeer"": @(
            @{
                ""PeerIP"": """",
                ""PeerExtASNUmber"": """"
            }
        ), 
    ""Pool"": @{ ""ResourceRef"": """" }
}"

## NOTES

## RELATED LINKS

[Get-NetworkControllerGateway](./Get-NetworkControllerGateway.md)

[Remove-NetworkControllerGateway](./Remove-NetworkControllerGateway.md)

