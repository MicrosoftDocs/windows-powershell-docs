---
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-IISSiteBinding

## SYNOPSIS
Adds a new binding to an existing Web site.

## SYNTAX

```
New-IISSiteBinding [-Name] <String> [-BindingInformation] <String> [[-Protocol] <String>]
 [[-CertificateThumbPrint] <String>] [[-SslFlag] <SslFlags>] [[-CertStoreLocation] <String>] [-Force]
 [-Passthru]
```

## DESCRIPTION
Adds a new binding to an existing Web site.

## EXAMPLES

### Example 1: Create a new HTTP binding
```
PS C:\> New-IISSiteBinding -Name "TestSite" -BindingInformation "*:8080:" -Protocol http
```

This command creates a new HTTP binding of "*:8080:" on a web site named TestSite

### Example 2: Create a new HTTPS binding
```
PS C:\> New-IISSiteBinding -Name "TestSite" -BindingInformation "*:443:" -CertificateThumbPrint "D043B153FCEFD5011B9C28E186A60B9F13103363" -CertStoreLocation "Cert:\LocalMachine\Webhosting" -Protocol https
```

This command creates a new HTTPS binding of "*:443:" on a web site named TestSite with a certificate of which thumbprint is D043B153FCEFD5011B9C28E186A60B9F13103363 and is saved on the Cert:\LocalMachine\Webhosting certificate store

### Example 3: Create a new HTTPS binding with setting SslFlag with "Sni, CentralCertStore" 
```
PS C:\> New-IISSiteBinding -Name "TestSite" "*:443:foo.com" -Protocol https -SslFlag "Sni, CentralCertStore"
```

This command creates a new HTTPS binding of "*:443:foo.com" on a web site named TestSite with enabling the SNI and CentralCertStore SSL flag settings


### Example 4: Create a new self signed certificate and used it for adding a new HTTPS binding for testing purpose
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

This powershell script example shows how to create a self-signed certificate on Personal store, export the certificate to ROOT store to make the certificate considered as a trusted certificate in the local machine and add a new HTTPS binding on a web site named TestSite for testing purpose.

## PARAMETERS

### -BindingInformation
{{Fill BindingInformation Description}}

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
{{Fill CertificateThumbPrint Description}}

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
{{Fill CertStoreLocation Description}}

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
{{Fill Force Description}}

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
{{Fill Name Description}}

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
{{Fill Passthru Description}}

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
{{Fill Protocol Description}}

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
{{Fill SslFlag Description}}

```yaml
Type: SslFlags
Parameter Sets: (All)
Aliases: 
Accepted values: None, Sni, CentralCertStore

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.String
Microsoft.Web.Administration.SslFlags


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

