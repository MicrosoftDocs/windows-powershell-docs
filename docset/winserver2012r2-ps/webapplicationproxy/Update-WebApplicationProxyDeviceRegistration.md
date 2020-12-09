---
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
online version: 
schema: 2.0.0
title: Update-WebApplicationProxyDeviceRegistration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 966F0141-96E7-40D2-AEFD-31F568867464
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Update-WebApplicationProxyDeviceRegistration

## SYNOPSIS
Configures the AD FS SSL endpoint listeners that correspond to the UPN suffixes.

## SYNTAX

```
Update-WebApplicationProxyDeviceRegistration [-NetworkCredential] <PSCredential> [<CommonParameters>]
```

## DESCRIPTION
The **Update-WebApplicationProxyDeviceRegistration** cmdlet discovers the user principal name (UPN) suffixes that you have set in Active Directory Federation Services (AD FS) and configures the AD FS Secure Sockets Layer (SSL) endpoint listeners that correspond to the UPN suffixes.
Any UPN suffix that the cmdlet discovers must have a corresponding registration name in the AD FS SSL certificate, in the form ienterpriseregistration.UpnSuffix.
You can also use a wild-card SSL certificate that covers all possible registration names.

## EXAMPLES

### Example 1: Configure AD FS SSL endpoint listeners
```
PS C:\>Update-WebApplicationProxyDeviceRegistration
```

This command discovers the UPN suffixes in AD FS and configures the SSL endpoint listeners that correspond to the UPN suffixes.

## PARAMETERS

### -NetworkCredential
Specifies a **PSCredential** object that contains the credentials of the AD FS identity that is authorized to register new the Federation server proxies.
By default, this is the account under which the Federation Service runs or an account that is a member of the administrators group on the federation server.

To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

