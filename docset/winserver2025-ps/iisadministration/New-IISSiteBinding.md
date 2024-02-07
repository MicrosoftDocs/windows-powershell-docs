---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
online version: https://learn.microsoft.com/powershell/module/iisadministration/new-iissitebinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-IISSiteBinding
---

# New-IISSiteBinding

## SYNOPSIS
Adds a new binding to an existing Website. This cmdlet has been introduced in version 1.1.0.0 of IISAdministration module.

## SYNTAX

```
New-IISSiteBinding [-Name] <String> [-BindingInformation] <String> [[-Protocol] <String>]
 [[-CertificateThumbPrint] <String>] [[-SslFlag] <SslFlags>] [[-CertStoreLocation] <String>] [-Force]
 [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
Adds a new binding to an existing website.

## EXAMPLES

### Example 1: Create a new HTTP binding
```
PS C:\> New-IISSiteBinding -Name "TestSite" -BindingInformation "*:8080:" -Protocol http
```

This command creates a new HTTP binding of "*:8080:" on a website named TestSite

### Example 2: Create a new HTTPS binding
```
PS C:\> New-IISSiteBinding -Name "TestSite" -BindingInformation "*:443:" -CertificateThumbPrint "D043B153FCEFD5011B9C28E186A60B9F13103363" -CertStoreLocation "Cert:\LocalMachine\Webhosting" -Protocol https
```

This command creates a new HTTPS binding of "*:443:" bindingInformation on a website named TestSite using an existing certificate which has a thumbprint of D043B153FCEFD5011B9C28E186A60B9F13103363 and
is placed at the Cert:\LocalMachine\Webhosting certificate store

### Example 3: Create a new HTTPS binding and set it with Sni and CentralCertStore SSL flag settings
```
PS C:\> New-IISSiteBinding -Name "TestSite" "*:443:foo.com" -Protocol https -SslFlag "Sni, CentralCertStore"
```

This command creates a new HTTPS binding of "*:443:foo.com" on a website named TestSite setting the SNI and CentralCertStore SSL flag settings


### Example 4: Create a new self signed certificate and use it for adding a new HTTPS binding for testing purpose
```
$password = "string1"  # put your password on string1
$hostName = "localhost"
$port = "443"
$storeLocation = "Cert:\LocalMachine\My"
$certificate = New-SelfSignedCertificate -DnsName $hostName -CertStoreLocation $storeLocation
$thumbPrint = $certificate.Thumbprint
$bindingInformation = "*:" + $port + ":" + $hostName
$certificatePath = ("cert:\localmachine\my\" + $certificate.Thumbprint)
$securedString = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-PfxCertificate -FilePath "C:\temp\temp.pfx" -Cert $certificatePath -Password $securedString
Import-PfxCertificate -FilePath "C:\temp\temp.pfx" -CertStoreLocation "Cert:\LocalMachine\Root" -Password $securedString
New-IISSiteBinding -Name "TestSite" -BindingInformation $bindingInformation -CertificateThumbPrint $thumbPrint -CertStoreLocation $storeLocation -Protocol https
```

This powershell script example shows how to create a self-signed certificate on Personal store. Export the certificate to ROOT store to make the certificate considered as a trusted certificate
in the local machine and add a new HTTPS binding on a website named TestSite for testing purposes.

## PARAMETERS

### -BindingInformation
Specifies the binding information string to use for the new site. The binding information of the form
IP:Port:hostname such as 192.168.0.1:80:www.contoso.com and one or more of the fields can be left blank, which
is equivalent to using a wildcard character such as \*:443:. In this representation \*  indicates all IP
addresses and all hostnames are indicated by leaving the corresponding field blank.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateThumbPrint
Specifies a certificate thumbprint, which is used to add a new HTTPS binding.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertStoreLocation
Specifies the certificate store path of the certificate, which is used to add a new HTTPS binding.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Cert:\LocalMachine\My, Cert:\LocalMachine\WebHosting, My, WebHosting

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -Name
Specifies the name of the IIS website.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Passthru
Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output.

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

### -Protocol
The protocol for which the binding is configured, usually http, https or ftp.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SslFlag
Specifies the SSL Flag(s) of the new binding.

```yaml
Type: SslFlags
Parameter Sets: (All)
Aliases:
Accepted values: None, Sni, CentralCertStore, DisableHTTP2, DisableOCSPStp, DisableQUIC, DisableTLS13, DisableLegacyTLS

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Web.Administration.SslFlags

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-IISSiteBinding](./Get-IISSiteBinding.md)

[Remove-IISSiteBinding](./Remove-IISSiteBinding.md)

[New-IISSite](./New-IISSite.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)
