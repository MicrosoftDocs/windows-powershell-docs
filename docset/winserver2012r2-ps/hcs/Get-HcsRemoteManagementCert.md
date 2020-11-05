---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-HcsRemoteManagementCert
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9B63432D-2D88-4977-A470-E8AC7DAAD889
---

# Get-HcsRemoteManagementCert

## SYNOPSIS
Gets the certificate for remote management.

## SYNTAX

```
Get-HcsRemoteManagementCert [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsRemoteManagementCert** cmdlet gets the certificate for Windows PowerShell® remote management.
Add the certificate to the trusted root certificate store on clients in order to connect to the device over HTTPS.
Copy the text into a .cer file to install the certificate by using the certificate import wizard.
Each device has a unique certificate.
You can regenerate a certificate by using the Set-HcsRemoteManagementCert cmdlet.
If you regenerate a certificate, the existing certificate becomes invalid.

## EXAMPLES

### Example 1: Get a certificate for remote management
```
PS C:\> Get-HcsRemoteManagementCert


-----BEGIN CERTIFICATE-----
MIIEIDCCAwigAwIBAgIQdPcK05gau6dNUMrOwzatvDANBgkqhkiG9w0BAQUFADCBpjEgMB4GA1UE
CwwXSGNzUmVtb3RlTWFuYWdlbWVudENlcnQxHjAcBgNVBAoMFU1pY3Jvc29mdCBDb3Jwb3JhdGlv
bjEjMCEGA1UEAwwaU0hYMDk5MTAxOEc0NEdTQ29udHJvbGxlcjExIzAhBgNVBAMMGlNIWDA5OTEw
MThHNDRHU0NvbnRyb2xsZXIwMRgwFgYDVQQDDA9TSFgwOTkxMDE4RzQ0R1MwIBcNMTQwMTI5MTQz
MDM5WhgPMjExMzAxMjkxNDMwMzlaMIGmMSAwHgYDVQQLDBdIY3NSZW1vdGVNYW5hZ2VtZW50Q2Vy
dDEeMBwGA1UECgwVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSMwIQYDVQQDDBpTSFgwOTkxMDE4RzQ0
R1NDb250cm9sbGVyMTEjMCEGA1UEAwwaU0hYMDk5MTAxOEc0NEdTQ29udHJvbGxlcjAxGDAWBgNV
BAMMD1NIWDA5OTEwMThHNDRHUzCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAMlWYYgr
MtWILKVb6H+IIgQI7ougZpjGqzCsamOspd/O+5lVgNQ7FrdRO+9seK34mD3GkbOvBmWo8TwOiX/E
B5gzPRiUjnrbLGkLgSyqH64fEFKXDYcSeFL0pqZqBF2dgacZsXvaQ/aySpVtTwspfVX2wFPfbSaR
Ov7T4AeKBSBSBqeMtrqtkt5w8CUc6e5bVyvW6qSz6fVE5NlGXJqUXfPMuzTwemzbc/GtleLj+RH0
sfYrp22V1AmwiFSCPptH5HBS2M9dQsp0fz6y3yS4FL/RtcNaksxaiCdUdZM2Id7n/EajHNdAMsLZ
hTI5nJORKhvSgzqfXYDXI8TTh5c0nUsCAwEAAaNGMEQwEwYDVR0lBAwwCgYIKwYBBQUHAwEwHQYD
VR0OBBYEFEySD/rMczXc5uc3O/X6tgSnXKgRMA4GA1UdDwEB/wQEAwIFIDANBgkqhkiG9w0BAQUF
AAOCAQEAXI24QXtRnUZyzKLgyp4gdidquohddboyvYWVExzPo8fG1D2f05v2k002XQCVXyPf0LV9
qBHpXnUhhNxLl1sV626NWrJRver/Aygki4Z8pn7hYvZQ0RYSGfnmBjDnh8wCdYbbVNZn/2E94et1
v2yb/gLFg3Qh4By06DKVUb6Zmc7p+A7SrNtFim7WdK9GeMqPrUdxXDk4OGyiWvzW9e07ipfr/yNL
aFNnUPpygXGWYo1QXdbohOBjngkvgBAmRGcF6xyBsceVyZt43dk/lx0Zxc4Ac4cH8WDz3H/MLdRJ
fkwYW7nncqgmE7JpON0/64W3KSwtgfGSltNiJeyeWAX0Rg==
-----END CERTIFICATE-----
```

This command gets the certificate to use for Windows PowerShell remote management.
Each device has a unique certificate.
You cannot copy this example output.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-HcsRemoteManagementCert](./Set-HcsRemoteManagementCert.md)

