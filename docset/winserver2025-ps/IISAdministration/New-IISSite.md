---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/new-iissite?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-IISSite
---

# New-IISSite

## SYNOPSIS
Creates an IIS Website.

## SYNTAX

```
New-IISSite [-Name] <String> [-PhysicalPath] <String> [-BindingInformation] <String> [[-Protocol] <String>]
 [[-CertificateThumbPrint] <String>] [[-SslFlag] <SslFlags>] [[-CertStoreLocation] <String>] [-Force]
 [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
The **New-IISSite** cmdlet is used to create an Internet Information Services (IIS) website with the given physical site as the root and binding information to listen on a specific IP:Port:Hostname binding.

## EXAMPLES

### Example 1: Add a new IIS web site
```
PS C:\> New-IISSite -Name "TestSite" -BindingInformation "*:8080:" -PhysicalPath "$env:systemdrive\inetpub\testsite"
```

This command creates a new website named TestSite.

### Example 2: Add a new website and set application pool of the site default application to a custom name
```
PS C:\> Start-IISCommitDelay
PS C:\> $TestSite = New-IISSite -Name TestSite -BindingInformation "*:8080:" -PhysicalPath "$env:systemdrive\inetpub\testsite" -Passthru
PS C:\> $TestSite.Applications["/"].ApplicationPoolName = "TestSiteAppPool"
PS C:\> Stop-IISCommitDelay
```

This command creates a website named TestSite with default application assigned to the TestSiteAppPool application pool.

### Example 3: Add a new website of HTTPS binding
```
PS C:\> New-IISSite -Name "TestSite" -PhysicalPath "$env:systemdrive\inetpub\testsite" -BindingInformation "*:443:" -CertificateThumbPrint "D043B153FCEFD5011B9C28E186A60B9F13103363" -CertStoreLocation "Cert:\LocalMachine\Webhosting" -Protocol https
```

This command creates a website named TestSite with HTTPS binding

## PARAMETERS

### -BindingInformation
Specifies the binding information string to use for the new site.
The binding information of the form IP:Port:hostname such as 192.168.0.1:80:www.contoso.com and one or more of the fields can be left blank, which is equivalent to using a wildcard character such as *:443:.
In this representation *  indicates all IP addresses and all hostnames are indicated by leaving the corresponding field blank.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateThumbPrint
Specifies a certificate thumbprint, which is used to add a new HTTPS binding

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertStoreLocation
Specifies the certificate store path of the certificate, which is used to add a new HTTPS binding

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Cert:\LocalMachine\My, Cert:\LocalMachine\WebHosting, My, WebHosting

Required: False
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -PhysicalPath
Specifies the physical path to the new IIS website.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
The protocol for which the binding is configured, usually http, https or ftp.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SslFlag
Specifies the SSL flag settings of the new binding.

```yaml
Type: SslFlags
Parameter Sets: (All)
Aliases:
Accepted values: None, Sni, CentralCertStore, DisableHTTP2, DisableOCSPStp, DisableQUIC, DisableTLS13, DisableLegacyTLS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Web.Administration.SslFlags

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-IISSite](./Get-IISSite.md)

[Remove-IISSite](./Remove-IISSite.md)

[Start-IISSite](./Start-IISSite.md)

[Stop-IISSite](./Stop-IISSite.md)

[New-IISSiteBinding](./New-IISSiteBinding.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

