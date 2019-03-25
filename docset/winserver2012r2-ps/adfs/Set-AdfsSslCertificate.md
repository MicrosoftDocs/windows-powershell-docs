---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Set-AdfsSslCertificate
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 78169996-C816-4F57-999A-7D11B963D1BE
---

# Set-AdfsSslCertificate

## SYNOPSIS
Sets an SSL certificate for HTTPS bindings for AD FS and the device registration service.

## SYNTAX

```
Set-AdfsSslCertificate -Thumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsSslCertificate** cmdlet sets an SSL certificate for HTTPS bindings for Active Directory Federation Services (AD FS) and, if configured, the device registration service.
The subject name of the specified certificate must match the federation service name.
Use this cmdlet to change the SSL certificate associated with the AD FS service.
You must run this cmdlet on each AD FS server in the AD FS farm.

## EXAMPLES

### Example 1: Set a certificate
```
PS C:\> Set-AdfsSslCertificate -Thumbprint "FC85DDB0FC58E63D8CB52654F22E4BE7900FE349"
```

This command sets the specified certificate for HTTPS bindings for AD FS and, if configured, the device registration service.

## PARAMETERS

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

### -Thumbprint
Specifies the thumbprint of a certificate.
The thumbprint that you specify corresponds to the certificate installed on the adfs2_fs in the local store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsSslCertificate](./Get-AdfsSslCertificate.md)

