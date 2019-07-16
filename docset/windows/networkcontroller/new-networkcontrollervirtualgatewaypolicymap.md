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
title: New-NetworkControllerVirtualGatewayPolicyMap
ms.reviewer:
ms.assetid: 94C7B143-8E97-444C-8FE8-CB2FFE007F25
---

# New-NetworkControllerVirtualGatewayPolicyMap

## SYNOPSIS
Creates a BGP routing policy map.

## SYNTAX

```
New-NetworkControllerVirtualGatewayPolicyMap [-VirtualGatewayId] <String> [-ResourceId] <String>
 [-Properties] <VGwPolicyMapProperties> [[-ResourceMetadata] <ResourceMetadata>] [[-Etag] <String>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerVirtualGatewayPolicyMap** cmdlet adds a configuration for a BGP routing policy map for the specified tenant to Network Controller.
If the policy map already exists, this cmdlet overwrites and replaces the older configuration.

## EXAMPLES

### Example 1: Add a new virtual gateway BGP routing policy map configuration to the Network Controller
```
PS C:\> $uri = "https://networkcontroller"

# Create a new object for policy map
PS C:\> $bgpPolicyMapPropertiesObject = New-Object Microsoft.Windows.NetworkController.VGwPolicyMapProperties 

# Update the policy map properties

# Add the new policy map for tenant
PS C:\> New-NetworkControllerVirtualGatewayPolicyMap -ConnectionUri $uri -VirtualGatewayId Contoso -ResourceId "Egress_Map" -Properties $ bgpPolicyMapPropertiesObject -Force
```

This command adds a new BGP routing policy map for the tenant Contoso.

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
Position: 6
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
Specifies the properties for the policy map.

```yaml
Type: VGwPolicyMapProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the virtual gateway policy map to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualGatewayId
Specifies the ID of a virtual gateway.

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

{

         ""PolicyName"" : """",

         ""PolicyType"": """",

         ""MatchCriteria"": @( @{

                  ""Clause"": """",

                  ""Operator"": ""And"",

                  ""Value"": """"

         } ), 

         ""SetActions"": @(@{

                  ""Clause"": """",

                  ""Value"": """"

         } ) 

}

## NOTES

## RELATED LINKS

[Get-NetworkControllerVirtualGatewayPolicyMap](./Get-NetworkControllerVirtualGatewayPolicyMap.md)

[Remove-NetworkControllerVirtualGatewayPolicyMap](./Remove-NetworkControllerVirtualGatewayPolicyMap.md)

