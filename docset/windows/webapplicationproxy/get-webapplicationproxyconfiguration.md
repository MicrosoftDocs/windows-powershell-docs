---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WebApplicationProxy-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WebApplicationProxyConfiguration
ms.reviewer:
ms.assetid: 6EE4F3B0-6A70-4DB4-BA36-EDCE8B546512
---

# Get-WebApplicationProxyConfiguration

## SYNOPSIS
Retrieves global Web Application Proxy settings.

## SYNTAX

```
Get-WebApplicationProxyConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplicationProxyConfiguration** cmdlet retrieves the Web Application Proxy settings that are not specific to any published application.
To modify the settings, use the Set-WebApplicationProxyConfiguration cmdlet.

## EXAMPLES

### Example 1: Retrieve the Web Application Proxy settings
```
PS C:\>Get-WebApplicationProxyConfiguration

ADFSTokenSigningCertificatePublicKey   : MIIFPzCCBCegAwIBAgIKJ95AmAAAAAA0djANBgkqhkiG9w0BAQUFADAWMRQwEgYDVQQDEwtBRFNUU1

RFU1RDQTAeFw0xMzA5MjQyMDU1MjZaFw0xNDA5MjQyMTA1MjZaMIGVMQswCQYDVQQGEwJVUzELMAkG

A1UECBMCV0ExEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbj

EbMBkGA1UECxMSRmVkZXJhdGVkIElkZW50aXR5MSowKAYDVQQDEyFoaWxvLjY3OS1zdHMubnR0ZXN0

Lm1pY3Jvc29mdC5jb20wggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC7CcA3g8eebYC792

NV1WtdTbhOHsS0llQSx6CY252NH0SgPtokUsI5D9MfIFccMzhZ75hDg1JIxOBZ6oAlX9qqc/oU1Lxy

7aeL1qluHwMGj7sLQSrBUTQgWEfD5grHY56JQgIcj1QU4TGGetOJt5WCeVZZ3lftRSo73STPfK9oqv

DMdB2guXs2yCMfQL2HORk/iJzXlklnaYisrVlEBWEkur5DYdaoQRXDAf6XwQH16VGYqoVzTbO4eObj

iOD9BSeXaHleVdOi1Gp10vbjDo3xbRLrxXIOl1/MF/LrgYtTxoz5cJVxzfHYl0PNpV0JrOSxCaYuPc

TI9Diu3Uolo4VFAgMBGAGjggINMIICCTBEBgkqhkiG9w0BCQ8ENzA1MA4GCCqGSIb3DQMCAgIAgDAO

BggqhkiG9w0DBAICAIAwBwYFKw4DAgcwCgYIKoZIhvcNAwcwHQYDVR0OBBYEFHloE9iHkCYWwkR/b0

DNntfOnQtHMA4GA1UdDwEB/wQEAwIFIDCBqgYDVR0RBIGiMIGfgjtFbnRlcnByaXNlRW5yb2xsbWVu

dC5ENjc5LURDLkFEVEVTVExBQi5OVFRFU1QuTUlDUk9TT0ZULkNPTYI9RW50ZXJwcmlzZVJlZ2lzdH

JhdGlvbi5ENjc5LURDLkFEVEVTVExBQi5OVFRFU1QuTUlDUk9TT0ZULkNPTYIhaGlsby42Nzktc3Rz

Lm50dGVzdC5taWNyb3NvZnQuY29tMB8GA1UdIwQYMBaAFIaWkB/0KC4pIjE+lbLsLSvCm+4RMG0GA1

UdHwRmMGQwYqBgoF6GLWh0dHA6Ly9hZHN0c3Rlc3RjYS9DZXJ0RW5yb2xsL0FEU1RTVEVTVENBLmNy

bIYtZmlsZTovL2Fkc3RzdGVzdGNhL0NlcnRFbnJvbGwvQURTVFNURVNUQ0EuY3JsMFUGCCsGAQUFBw

EBBEkwRzBFBggrBgEFBQcwAoY5ZmlsZTovL2Fkc3RzdGVzdGNhL0NlcnRFbnJvbGwvYWRzdHN0ZXN0

Y2FfQURTVFNURVNUQ0EuY3J0MA0GCSqGSIb3DQEBBQUAA4IBAQAn7bK+JINXK/E9wp8kCqQhgZGCTR

i38YnBrkI9v5+g7Tr02Rp0V03Tr9KIQwTcptSIdGOhaxBJKpm7XAYE2tL0Kc5LNUsk70dJdjBuvYfa

C81phw3+ogBABfqt464BfzAsX+guePadQI522BFJsbxWbEXHDLb6BpNUsiyQh4FSlkNH1B7y7QALbx

1Qe9IQBYaDyHf3a9MAWAKcaPD6VLwOnpyDCopCZ20T5H40Sel+wQfefMrUYXLqlS7fant3G1SfT2Ob

Uu60l+M06i8Wd15gh/ZZo/n+phJQs/L58XExEwHmycrL6fb5zdPHUH/VcMQlDYfGjUEvuXVAkrDHD6

eo

ADFSUrl                                : https://sts.contoso.com/adfs/ls

ADFSWebApplicationProxyRelyingPartyUri : urn:AppProxy:com

ConfigurationChangesPollingIntervalSec : 30

ConnectedServersName                   : {WAP-server1.corp.contoso.com, WAP-server2.corp.contoso.com}

OAuthAuthenticationURL                 : https://sts.contoso.com/adfs/oauth2/authorize /
```

This command retrieves the Web Application Proxy settings.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#AppProxyGlobalConfiguration
Displays the Web Application Proxy configuration.

## NOTES

## RELATED LINKS

[Web Application Proxy overview](http://technet.microsoft.com/library/dn280944.aspx)

[Publishing Internal Applications using Web Application](http://technet.microsoft.com/library/dn383650.aspx)

[Set-WebApplicationProxyConfiguration](./Set-WebApplicationProxyConfiguration.md)

