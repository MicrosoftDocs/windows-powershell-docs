---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AdfsSslCertificate
ms.assetid: 78169996-C816-4F57-999A-7D11B963D1BE
---

# Set-AdfsSslCertificate

## SYNOPSIS
Sets an SSL certificate for HTTPS bindings for AD FS.

## SYNTAX

```
Set-AdfsSslCertificate -Thumbprint <String> [-Member <String[]>] [-Force <Boolean>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsSslCertificate** cmdlet sets an SSL certificate for HTTPS bindings for Active Directory Federation Services (AD FS).
Use this cmdlet to change the SSL certificate associated with the AD FS service.
You must run this cmdlet on each AD FS server in the AD FS farm.

Use this cmdlet to change the deployment from one in which both user certificate authentication and device certificate authentication use port 443, to one in which user certificate authentication uses a non-standard port.
Specify a new certificate that does not contain a Subject Alternative Name (SAN) for `certauth`.\<federation service name\>, as in `certauth.contoso.com`.

## EXAMPLES

### Example 1: Set a certificate
```
PS C:\> Set-AdfsSslCertificate -Thumbprint "FC85DDB0FC58E63D8CB52654F22E4BE7900FE349"
```

This command sets the specified certificate for HTTPS bindings for AD FS.

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

### -Force


```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Member


```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of a certificate.
The thumbprint that you specify corresponds to the certificate installed on the federation server in the local store.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsSslCertificate](./Get-AdfsSslCertificate.md)

