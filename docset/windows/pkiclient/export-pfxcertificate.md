---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Export-PfxCertificate
ms.reviewer:
ms.assetid: 7E97BC6B-B6E0-4BCA-98CE-E83D307FA3A6
---

# Export-PfxCertificate

## SYNOPSIS
Exports a certificate or a PFXData object to a Personal Information Exchange (PFX) file.

## SYNTAX

### PfxCert
```
Export-PfxCertificate [-NoProperties] [-NoClobber] [-Force] [-ChainOption <ExportChainOption>]
 [-ProtectTo <String[]>] [-Password <SecureString>] [-FilePath] <String> [-PFXData] <PfxData> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### NormalCert
```
Export-PfxCertificate [-NoProperties] [-NoClobber] [-Force] [-ChainOption <ExportChainOption>]
 [-ProtectTo <String[]>] [-Password <SecureString>] [-FilePath] <String> [-Cert] <Certificate> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-PfxCertificate** cmdlet exports a certificate or a **PFXData** object to a Personal Information Exchange (PFX) file.
By default, extended properties and the entire chain are exported.

Delegation may be required when using this cmdlet with Windows PowerShell® remoting and changing user configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText



PS C:\>Get-ChildItem -Path cert:\localMachine\my\5F98EBBFE735CDDAE00E33E0FD69050EF9220254 | Export-PfxCertificate -FilePath C:\mypfx.pfx -Password $mypwd
```

This example exports a certificate from the local machine store to a PFX file which includes the entire chain and all external properties.

### EXAMPLE 2
```
PS C:\>$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText



PS C:\>Get-ChildItem -Path cert:\LocalMachine\my | Export-PfxCertificate -FilePath C:\mypfx.pfx -Password $mypwd
```

This example exports all certificates under the My store for the machine account into one file named mypfx.pfx.
In order for this cmdlet to succeed, all keys need to be exportable.

### EXAMPLE 3
```
PS C:\>$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText



PS C:\>Export-PfxCertificate -Cert cert:\currentuser\my\5F98EBBFE735CDDAE00E33E0FD69050EF9220254 -FilePath c:\myexport.pfx -ChainOption EndEntityCertOnly -NoProperties -Password $mypwd
```

This example exports a certificate from the current user store with no chain and no external properties

### EXAMPLE 4
```
PS C:\>$a = Get-ChildItem -Path cert:\localMachine\my 
Export-PfxCertificate -Cert $a[1] -FilePath C:\myexport.pfx -ProtectTo "contoso\billb99", "contoso\johnj99"
```

This example exports a certificate from the current machine store.
Both user accounts, contos\billb99 and contos\johnj99, can access this PFX with no password.
A Windows® 8 DC for key distribution is required.

### EXAMPLE 5
```
PS C:\>$a = Get-ChildItem -Path cert:\localMachine\my



PS C:\>$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText



PS C:\>Export-PfxCertificate -Cert $a[1] -FilePath C:\myexport.pfx -ProtectTo "contoso\billb99", "contoso\johnj99" -Password $mypwd
```

This example exports a certificate from the current machine store.
Both user accounts, johnj99 and billb99, can access this PFX file with no password.
For everyone else, they need to use 1234 as a password.
A Windows 8 DC for key distribution is required.

### EXAMPLE 6
```
PS C:\>$NewPwd = ConvertTo-SecureString -String "abcd" -Force -AsPlainText



PS C:\>$mypfx = Get-PfxData -FilePath C:\mypfx.pfx -Password $Oldpwd



PS C:\>Export-PfxCertificate -PFXData $mypfx -FilePath C:\mypfx2.pfx -Password $NewPwd
```

This example changes an existing password for a PFX file from $OldPwd to $NewPwd.

## PARAMETERS

### -Cert
Specifies the path to the certificate to be exported.

```yaml
Type: Certificate
Parameter Sets: NormalCert
Aliases: PsPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ChainOption
Specifies the options for building a chain when exporting certificates.
The acceptable values for this parameter are:

 -- BuildChain:  Certificate chain for all end entity certificates will be built and included in the export.
This option is valid for both **PfxData** and **Cert** parameters.
In the case of **PfxData** parameter, the collection of all PFX certificates will be used as an additional store. 

 -- EndEntityCertOnly: Only end entity certificates are exported without any chain.
This option is valid for both the **PfxData** and the **Cert** parameters. 

 -- PfxDataOnly: Certificates contained in **PFXData** objects will be exported with no chain building.
This option is only valid when the **PfxData** parameter is used.

```yaml
Type: ExportChainOption
Parameter Sets: (All)
Aliases: 
Accepted values: BuildChain, EndEntityCertOnly, PfxDataOnly

Required: False
Position: Named
Default value: None
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

### -FilePath
Specifies the path for the PFX file to be exported.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies that the provided PFX file should be overwritten, even if the Read-only attribute is set on the file.
By default, this cmdlet overwrites existing PFX files without warning, unless the Read-only or hidden attribute is set or the **NoClobber** parameter is used in the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber
Specifies that if the PFX file already exists, it should not be over written.
This parameter takes precedence over the **Force** parameter, which permits this cmdlet to overwrite a PFX file even if it has the Read-only attribute set.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoProperties
Specifies whether the extended properties for a certificate are exported.
If this parameter is specified, then extended properties are not included with the export.
By default, all extended properties are included in the exported file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PFXData
Specifies a **PFXData** object that contains one or more certificates from a PFX file.

```yaml
Type: PfxData
Parameter Sets: PfxCert
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Password
Specifies the password used to protect the exported PFX file.
The password should be in the form of secure string.
Either the **ProtectTo** or this parameter must be specified, or an error will be displayed.

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

### -ProtectTo
Specifies an array of strings for the username or group name that can access the private key of PFX file without any password.
This requires a Windows Server® 2012 domain controller.
Either the **Password** or this parameter must be specified, or an error will be displayed.

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

### System.Security.Cryptography.X509Certificates.X509Certificate2[]
The **X509Certificate2\[\]** object is an array of certificate objects.

## OUTPUTS

### System.IO.FileInfo
The **FileInfo** object contains the information about the PFX file.

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](http://go.microsoft.com/fwlink/p/?LinkId=293933)

[Get-ChildItem](http://go.microsoft.com/fwlink/p/?LinkId=290488)

[Get-PfxData](./Get-PfxData.md)

[Import-PfxCertificate](./Import-PfxCertificate.md)

