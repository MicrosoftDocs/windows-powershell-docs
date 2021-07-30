---
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: pki
online version: https://docs.microsoft.com/powershell/module/pki/import-pfxcertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-PfxCertificate

## SYNOPSIS
Imports certificates and private keys from a Personal Information Exchange (PFX) file to the destination store.

## SYNTAX

```
Import-PfxCertificate [-Exportable] [-Password <SecureString>] [[-CertStoreLocation] <String>]
 [-FilePath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-PfxCertificate** cmdlet imports certificates and private keys from a PFX file to the destination store.
Certificates with and without private keys in the PFX file are imported, along with any external properties that are present.

Delegation may be required when using this cmdlet with Windows PowerShell® remoting and changing user configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText



PS C:\>Import-PfxCertificate -FilePath C:\mypfx.pfx cert:\localMachine\my -Password $mypwd
```

This example imports the PFX file my.pfx with a private non-exportable key into the My store for the machine account.

### EXAMPLE 2
```
PS C:\>Get-ChildItem -Path c:\mypfx\my.pfx | Import-PfxCertificate -CertStoreLocation Cert:\CurrentUser\My -Exportable
```

This example imports the PFX file my.pfx with a private non-exportable key into the My store for the current user with private key exportable.
The **Password** parameter is not required since this PFX file is not password protected.

### EXAMPLE 3
```
PS C:\>Set-Location -Path cert:\localMachine\my



PS C:\>Import-PfxCertificate -FilePath c:\mypfx.pfx
```

This example imports the PFX file mypfx.pfx into the My store for the machine account.
The **Password** parameter is not required since this PFX file is protected using the domain account of this machine.
This requires a Windows Server® 2012 domain controller.

## PARAMETERS

### -CertStoreLocation
Specifies the path of the store to which certificates will be imported.
If this parameter is not specified, then the current path is used as the destination store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
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

### -Exportable
Specifies whether the imported private key can be exported.
If this parameter is not specified, then the private key cannot be exported.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the path for the PFX file.

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
Specifies the password for the imported PFX file in the form of a secure string.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
A String containing the path to the PFX file.

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2
The imported X509Certificate2 object contained in the PFX file that is associated with private keys.

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkID=113291)

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=204557)

[Set-Location](https://go.microsoft.com/fwlink/p/?LinkID=113397)

[Export-PfxCertificate](./Export-PfxCertificate.md)

