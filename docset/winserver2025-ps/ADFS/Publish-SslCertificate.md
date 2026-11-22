---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/publish-sslcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-SslCertificate
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-AdfsSslCertificate](./Set-AdfsSslCertificate.md)

