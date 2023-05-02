---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: pki
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/export-certificate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Certificate
---

# Export-Certificate

## SYNOPSIS
Exports a certificate from a certificate store into a file.

## SYNTAX

```
Export-Certificate [-Type <CertType>] [-NoClobber] [-Force] -FilePath <String>
 -Cert <Certificate> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Export-Certificate` cmdlet exports a certificate from a certificate store to a file. The
private key is not included in the export. If more than one certificate is being exported, then the
default file format is `SST`. Otherwise, the default format is `CERT`. Use the **Type** parameter to
change the file format.

## EXAMPLES

### EXAMPLE 1

```powershell
$cert = Get-ChildItem -Path Cert:\CurrentUser\My\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

Export-Certificate -Cert $cert -FilePath C:\Certs\user.sst -Type SST
```

This example exports a certificate to the file system as a Microsoft serialized certificate store
without its private key.

### EXAMPLE 2

```powershell
$cert = Get-ChildItem -Path Cert:\CurrentUser\My\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

Export-Certificate -Cert $cert -FilePath C:\Certs\user.cer
```

This example exports a certificate to the file system as a DER-encoded `.cer` file without its
private key.

### EXAMPLE 3

```powershell
$cert = Get-ChildItem -Path Cert:\CurrentUser\My\EEDEF61D4FF6EDBAAD538BB08CCAADDC3EE28FF

Export-Certificate -Cert $cert -FilePath C:\Certs\user.p7b -Type p7b
```

This example exports a certificate to the file system as a PKCS#7-formatted `.p7b` file without its
private key.

### EXAMPLE 4

```powershell
Get-ChildItem -Path Cert:\CurrentUser\My |
    Export-Certificate -FilePath C:\Certs\allcerts.sst -Type SST
```

This example exports all certificates under the `Cert:\CurrentUser\My` store into a Microsoft
serialized certificate store `allcerts.sst`.

## PARAMETERS

### -Cert

Specifies one or more certificates to be exported to a file. A single certificate object, an array
of certificate objects, or a path to one or more certificates in a certificate store can be
specified.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -FilePath

Specifies the location where the exported certificate will be stored.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Specifies that the exported certificate file will overwrite an existing certificate file, even if it
has the Read-only attribute set. The **NoClobber** parameter takes precedence over this parameter
when both are used.

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

### -NoClobber

Prevents an exported certificate file from overwriting an existing certificate file. This parameter
takes precedence over the **Force** parameter, which permits this cmdlet to overwrite an existing
certificate file, even if it has the Read-only attribute set.

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

### -Type

Specifies the type of output file for the certificate export as follows.

- `SST`: A Microsoft serialized certificate store (`.sst`) file format which can contain one or
  more certificates. This is the default value for multiple certificates.
- `CERT`: A `.cer` file format which contains a single DER-encoded certificate. This is the
 default value for one certificate.

- `P7B`: A PKCS#7 file format which can contain one or more certificates.

```yaml
Type: Microsoft.CertificateServices.Commands.CertType
Parameter Sets: (All)
Aliases: 
Accepted values: SST, CERT, P7B

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

### System.Security.Cryptography.X509Certificates.X509Certificate2

A Certificate object can be piped into to this cmdlet.

## OUTPUTS

### System.IO.FileInfo

The **FileInfo** object contains the information about the certificate file.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/?LinkId=290488)

[Import-Certificate](./Import-Certificate.md)
