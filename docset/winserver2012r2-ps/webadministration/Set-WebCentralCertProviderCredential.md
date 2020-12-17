---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Set-WebCentralCertProviderCredential
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D0323D6F-2D42-49EE-93CA-9B4B1EB8663C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WebCentralCertProviderCredential

## SYNOPSIS
Changes the user-account credentials for the central certificate provider.

## SYNTAX

```
Set-WebCentralCertProviderCredential [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebCentralCertProviderCredential** cmdlet changes the user-account credentials (user name and password) for the central certificate provider.

## EXAMPLES

### Example 1: Set credentials
```
PS C:\>Set-WebCentralCertProviderCredentials -UserName "CertStoreUser"
UserName=CertStoreUser

Password=

*********

Confirm Password=

*********
```

This command changes the user-account credentials for the central certificate store.

## PARAMETERS

### -UserName
Specifies the password of the user account that is used to access the central certificate store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

