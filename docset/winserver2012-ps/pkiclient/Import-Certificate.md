---
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
ms.assetid: 5BACC9D9-2D47-40AE-B70D-2CC8A788310D
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
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
PS C:\>$file = ( Get-ChildItem -Path C:\files\root.cer )



PS C:\>$file | Import-Certificate -CertStoreLocation cert:\CurrentUser\Root
```

This example imports the certificate from the file into the root store of the current user.

### EXAMPLE 2
```
PS C:\>Set-Location -Path cert:\CurrentUser\My



PS C:\>Import-Certificate -Filepath "C:\files\intermediate.cert"
```

This example imports the certificate from the file into the current store.

## PARAMETERS

### -CertStoreLocation
Specifies the path to the certificate store where the certificates will be imported.
If the path to the certificate store is not specified, then the current store is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -FilePath
Specifies the path to a certificate file to be imported.
Acceptable formats include .sst, .p7b, and .cert files.
If the file contains multiple certificates, then each certificate will be imported to the destination store.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
A String containing the file path.

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2[]
The output is an array of X509Certificate2\[\] objects.

## NOTES

## RELATED LINKS

[Get-ChildItem](http://go.microsoft.com/fwlink/p/?LinkId=204557)

[Set-Location](http://go.microsoft.com/fwlink/p/?LinkId=113397)

[Export-Certificate](./Export-Certificate.md)

