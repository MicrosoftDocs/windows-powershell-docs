---
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-IISSiteBinding

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

```
New-IISSiteBinding [-Name] <String> [-BindingInformation] <String> [[-Protocol] <String>]
 [[-CertificateThumbPrint] <String>] [[-SslFlag] <SslFlags>] [[-CertStoreLocation] <String>] [-Force]
 [-Passthru]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1: Create a new HTTP binding
```
PS C:\> New-IISSiteBinding -Name "TestSite" -BindingInformation "*:8080:" -Protocol http
```

This command creates a new HTTP binding of "*:8080:" on to a web site named TestSite

### Example 2: Create a new HTTPS binding
```
PS C:\> New-IISSiteBinding -Name "TestSite" -BindingInformation "*:443:" -CertificateThumbPrint "D043B153FCEFD5011B9C28E186A60B9F13103363" -CertStoreLocation "Cert:\LocalMachine\Webhosting" -Protocol https
```

This command creates a new HTTPS binding of "*:443:" on to a web site named TestSite with a certificate of which thumbprint is D043B153FCEFD5011B9C28E186A60B9F13103363 and is saved on the Cert:\LocalMachine\Webhosting certificate store

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

