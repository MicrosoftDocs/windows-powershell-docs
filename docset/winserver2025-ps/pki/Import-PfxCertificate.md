---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/import-pfxcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PfxCertificate
---

# Import-PfxCertificate

## SYNOPSIS
Imports certificates and private keys from a Personal Information Exchange (PFX) file to the
destination store.

## SYNTAX

```
Import-PfxCertificate [-Exportable] [-Password <SecureString>]
 [[-CertStoreLocation] <String>] [-FilePath] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Import-PfxCertificate` cmdlet imports certificates and private keys from a PFX file to the
destination store. Certificates with and without private keys in the PFX file are imported, along
with any external properties that are present.

Delegation may be required when using this cmdlet with Windows PowerShell remoting and changing user
configuration.

## EXAMPLES

### EXAMPLE 1

```powershell
$mypwd = Get-Credential -UserName 'Enter password below' -Message 'Enter password below'

$params = @{
    FilePath = 'C:\mypfx.pfx'
    CertStoreLocation = 'Cert:\LocalMachine\My'
    Password = $mypwd.Password
}
Import-PfxCertificate @params
```

This example imports the PFX file `mypfx.pfx` with a private, non-exportable key into the My store
for the machine account.

### EXAMPLE 2

```powershell
Get-ChildItem -Path C:\mypfx.pfx |
    Import-PfxCertificate -CertStoreLocation Cert:\CurrentUser\My -Exportable
```

This example imports the PFX file `mypfx.pfx` with a private, exportable key into the My store for
the current user. The **Password** parameter is not required since this PFX file is not password
protected.

### EXAMPLE 3

```powershell
Set-Location -Path Cert:\LocalMachine\My

Import-PfxCertificate -FilePath C:\mypfx.pfx
```

This example imports the PFX file `mypfx.pfx` into the My store for the machine account. The
**Password** parameter is not required since this PFX file is protected using the domain account of
this machine. This requires a Windows Server 2012 or later domain controller.

## PARAMETERS

### -CertStoreLocation

Specifies the path of the store to which certificates will be imported. If this parameter is not
specified, then the current path is used as the destination store.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exportable

Specifies whether the imported private key can be exported. If this parameter is not specified, then
the private key cannot be exported.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Specifies the path for the PFX file.

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

Specifies the password for the imported PFX file in the form of a secure string.

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

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

A **String** containing the path to the PFX file.

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2

The imported **X509Certificate2** object contained in the PFX file that is associated with private
keys.

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkID=293933)

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=290488)

[Set-Location](https://go.microsoft.com/fwlink/p/?LinkID=293912)

[Export-PfxCertificate](./Export-PfxCertificate.md)

[System Store Locations](/windows/desktop/seccrypto/system-store-locations)
