---
external help file: Microsoft.FederationServices.Deployment.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/install-adfsstandalone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-AdfsStandalone

## SYNOPSIS
Sets up this computer as a stand-alone federation server for evaluation purposes or for a small lab environment.

## SYNTAX

### ADFSStandAloneEnableAutoCertRollover (Default)
```
Install-AdfsStandalone -CertificateThumbprint <String> -FederationServiceName <String>
 [-OverwriteConfiguration] [-SSLPort <Int32>] [<CommonParameters>]
```

### ADFSStandAloneDisableAutoCertRollover
```
Install-AdfsStandalone -CertificateThumbprint <String> -DecryptionCertificateThumbprint <String>
 -FederationServiceName <String> [-OverwriteConfiguration] -SigningCertificateThumbprint <String>
 [-SSLPort <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Install-AdfsStandalone cmdlet sets up this computer as a stand-alone federation server for evaluation purposes or for a small lab environment.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$fscredential = Get-Credential
C:\PS>Install-AdfsStandalone -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -DecryptionCertificateThumbprint ‎049e0546ca9a63d7fb5a193ccaec29badc125176 -SigningCertificateThumbprint ‎059d9546ca9a63d7fb5a193ccaec29badc236358 -ServiceAccountCredential $fscredential
```

Description

-----------

Installs a standalone AD FS server with federation service name and all certificates specified, including those that are needed to sign and decrypt AD FS service communications.

## PARAMETERS

### -CertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used in the SSL binding of the Default Web Site in IIS. 
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DecryptionCertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used for token decryption. 
If this parameter is used, the automatic certificate rollover feature will be disabled, and a token signing certificate must also be specified using the SigningCertificateThumbprint parameter. 
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: ADFSStandAloneDisableAutoCertRollover
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationServiceName
Specifies the DNS name of the federation service. 
This value must match the subject name of the certificate configured on the SSL binding in IIS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverwriteConfiguration
This parameter must be used to remove an existing AD FS configuration database and overwrite it with a new database.

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

### -SSLPort
Specifies the value of the port number of the SSL binding that the AD FS web site will use.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 443
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used for token signing. 
If this parameter is used, the automatic certificate rollover feature will be disabled, and a token decryption certificate must also be specified using the DecryptionCertificateThumbprint parameter. 
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: ADFSStandAloneDisableAutoCertRollover
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

### none

## OUTPUTS

### Result object

## NOTES

## RELATED LINKS

