---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: pki
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/import-certificate?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Certificate
---

# Import-Certificate

## SYNOPSIS
Imports one or more certificates into a certificate store.

## SYNTAX

```
Import-Certificate [-FilePath] <String> [-CertStoreLocation <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-Certificate** cmdlet imports one or more certificates into a certificate store.

## EXAMPLES

### EXAMPLE 1
```
Import-Certificate -FilePath "C:\Users\xyz\Desktop\BackupCert.Cer" -CertStoreLocation cert:\CurrentUser\Root
```

This example imports the certificate from the file into the root store of the current user.

### EXAMPLE 2
```
PS C:\>Set-Location -Path cert:\CurrentUser\My

PS cert:\CurrentUser\My>Import-Certificate -Filepath "C:\files\intermediate.cert"
```

This example imports the certificate from the file into the current store.

### EXAMPLE 3
```
Import-Certificate -FilePath "C:\Users\Xyz\Desktop\BackupCert.Cer" -CertStoreLocation Cert:\LocalMachine\Root
```

This example imports the certificate from the file into the root store of the Local Machine.

## PARAMETERS

### -CertStoreLocation
Specifies the path to the certificate store where the certificates will be imported.
If the path to the certificate store is not specified, then the current store is used.
In order to get a list of valid CertStoreLocation values, open Powershell and run "cd cert:". Afterwards type "dir".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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
Specifies the path to a certificate file to be imported.
Acceptable formats include .sst, .p7b, and .cert files.
If the file contains multiple certificates, then each certificate will be imported to the destination store.
The file must be in .sst format to import multiple certificates;
otherwise, only the first certificate in the file will be imported.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
A **String** containing the file path.

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2[]
The output is an array of **X509Certificate2\[\]** objects.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=290488)

[Set-Location](https://go.microsoft.com/fwlink/p/?LinkId=293912)

[Export-Certificate](./Export-Certificate.md)

[System Store Locations](/windows/desktop/seccrypto/system-store-locations)
