---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: pki
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/get-pfxdata?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxData
---

# Get-PfxData

## SYNOPSIS
Extracts the content of a Personal Information Exchange (PFX) file into a structure without
importing it to certificate store.

## SYNTAX

```
Get-PfxData [-Password <SecureString>] [-FilePath] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Get-PfxData` cmdlet extracts the content of a Personal Information Exchange (PFX) file into a
structure that contains the end entity certificate, and any intermediate and root certificates.

## EXAMPLES

### EXAMPLE 1

```powershell
$mypwd = ConvertTo-SecureString -String '1234' -Force -AsPlainText

$mypfx = Get-PfxData -FilePath C:\mypfx.pfx -Password $mypwd
```

This example returns certificate information for the file `C:\mypfx.pfx` that is secured with the
specified password.

### EXAMPLE 2

```powershell
$NewPwd = ConvertTo-SecureString -String 'abcd' -Force -AsPlainText

$mypfx = Get-PfxData -FilePath C:\mypfx.pfx -Password $OldPwd

Export-PfxCertificate -PfxData $mypfx -FilePath C:\mypfx.pfx -Password $NewPwd -Force
```

This example shows how one can change an existing password for `mypfx.pfx` file from `$OldPwd` to
`$NewPwd`.

## PARAMETERS

### -FilePath

Specifies the path to the PFX file.

```yaml
Type: System.String
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
Type: System.SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

A string containing the path to PFX file.

## OUTPUTS

### Microsoft.CertificateServices.Commands.PFXData

A **PFXData** object.

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkID=293933)

[Export-PfxCertificate](./Export-PfxCertificate.md)
