---
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Publish-SslCertificate
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 06868ED8-D84C-4BD4-9848-84378ECB99A0
---

# Publish-SslCertificate

## SYNOPSIS
The Publish-SslCertificate cmdlet is deprecated.
Instead, use the Set-AdfsSslCertificate cmdlet.

## SYNTAX

### PublishByPfxPath (Default)
```
Publish-SslCertificate -Path <String> -Password <SecureString> [<CommonParameters>]
```

### PublishByPfxData
```
Publish-SslCertificate -RawPfx <Byte[]> -Password <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **Publish-SslCertificate** cmdlet is deprecated in this release.
Instead, use the Set-AdfsSslCertificate cmdlet.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Password
```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
```yaml
Type: String
Parameter Sets: PublishByPfxPath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RawPfx
```yaml
Type: Byte[]
Parameter Sets: PublishByPfxData
Aliases: 

Required: True
Position: Named
Default value: None
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

[Set-AdfsSslCertificate](./Set-AdfsSslCertificate.md)

