---
author: brianlic-msft
description: 
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: New-NetworkControllerAccessControlList
ms.assetid: 5040E9B9-D832-47A5-BB62-4B20C54760D1
---

# New-NetworkControllerAccessControlList

## SYNOPSIS
Creates an ACL for a Network Controller.

## SYNTAX

```
New-NetworkControllerAccessControlList [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <AccessControlListProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>]
 [-Force] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerAccessControlList** cmdlet creates an access control list (ACL) for a Network Controller.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint of a digital public key X.509 certificate of a user account that has permission to perform this action.
In order for Network Controller to authorize the account, specify this thumbprint by using the *ClientCertificateThumbprint* parameter of the Install-NetworkController or Set-NetworkController cmdlet.

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
Specifies the Uniform Resource Identifier (URI) of the Network Controller that all Representational State Transfer (REST) clients use to connect to that controller.

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
This user must be a member of in the security group specified by the *ClientSecurityGroup* parameter of the Install-NetworkController cmdlet.

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
Specifies properties of the ACL.

```yaml
Type: AccessControlListProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the ACL.

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
Specifies metadata for the resource.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetworkControllerAccessControlList](./Get-NetworkControllerAccessControlList.md)

