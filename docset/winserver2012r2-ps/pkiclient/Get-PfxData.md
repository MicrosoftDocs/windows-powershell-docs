---
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
online version: 
schema: 2.0.0
title: Get-PfxData
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 654BB02E-B277-4497-AD58-BEAA73B725B5
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-PfxData

## SYNOPSIS
Extracts the content of a Personal Information Exchange (PFX) file into a structure without importing it to certificate store.

## SYNTAX

```
Get-PfxData [-Password <SecureString>] [-FilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-PfxData** cmdlet extracts the content of a Personal Information Exchange (PFX) file into a structure that contains the end entity certificate, any intermediate and root certificates.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText



PS C:\>$mypfx = Get-PfxData -FilePath C:\mypfx.pfx -Password $mypwd
```

This example returns certificate information for the file mypfx.pfx located on the C: drive that is secured with the specified password.

### EXAMPLE 2
```
PS C:\>$NewPwd = ConvertTo-SecureString -String "abcd" -Force -AsPlainText



PS C:\>$mypfx = Get-PfxData -FilePath C:\mypfx.pfx -Password $Oldpwd



PS C:\>Export-PfxCertificate -PfxData $mypfx -FilePath C:\mypfx.pfx -Password $NewPwd -Force
```

This example shows how one can change an existing password for mypfx.pfx file from $OldPwd to $NewPwd.

## PARAMETERS

### -FilePath
Specifies the path to the PFX file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies the password for the imported PFX file.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
A string containing the path to PFX file.

## OUTPUTS

### Microsoft.CertificateServices.Commands.PFXData
A PFXData object.

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkID=293933)

[Export-PfxCertificate](./Export-PfxCertificate.md)

