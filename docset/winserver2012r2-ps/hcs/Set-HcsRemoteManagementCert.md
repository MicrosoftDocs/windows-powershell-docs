---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-HcsRemoteManagementCert
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6D701AD0-5AA0-4A6E-811C-839CA6E44C7B
---

# Set-HcsRemoteManagementCert

## SYNOPSIS
Generates the certificate for remote management.

## SYNTAX

```
Set-HcsRemoteManagementCert [-CN <String[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsRemoteManagementCert** cmdlet generates the certificate for Windows PowerShell® remote management.
This cmdlet creates a new certificate and invalidates the old certificate.
After the cmdlet finishes, you must install the new certificate on all client machines, and update their hosts files to map the values specified by the **CN** parameter.

## EXAMPLES

### Example 1: Generate a certificate
```
PS C:\> Set-HcsRemoteManagementCert
-----BEGIN CERTIFICATE-----
MIIDfjCCAmagAwIBAgIQG9kCqAtZco1OANvk9P7lPjANBgkqhkiG9w0BAQUFADBWMSAwHgYDVQQL
DBdIY3NSZW1vdGVNYW5hZ2VtZW50Q2VydDEeMBwGA1UECgwVTWljcm9zb2Z0IENvcnBvcmF0aW9u
MRIwEAYDVQQDDAkxMjM0NTY3ODkwIBcNMTQwMjA1MTEyOTI1WhgPMjExMzAyMDUxMTI5MjVaMFYx
IDAeBgNVBAsMF0hjc1JlbW90ZU1hbmFnZW1lbnRDZXJ0MR4wHAYDVQQKDBVNaWNyb3NvZnQgQ29y
cG9yYXRpb24xEjAQBgNVBAMMCTEyMzQ1Njc4OTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoC
ggEBAMrKCQgT0TONnakvNLr6+WJRQZFwTlRxFBxeT3JBHBFOiDupXjVIK0NMjH3sGWpcx8Mkeq69
qO+qMfEE+HHodOwrzrvW5KmqZe4XdYmc+U5mdLF/AqTTrPKvb8+dfOC+Zximzu7stOgZrPlY2QBx
Ml/MVcxLcqhud5PzIImV9gT7P1uULuQaOcAibveort7MlA8f77x6WakQOBmyH/mR2rWiwlE/KvR+
EDGHTtcWwsqL7hZMee8epRKwTyfXfzT83z77a3pe5kN7w4Z2JKVFM9b3SS1ANCbhupBZXVSNUuNF
2obB8TVARMV16nm4DtALLqIU4GQCyAJ6OfZejnDP2rsCAwEAAaNGMEQwEwYDVR0lBAwwCgYIKwYB
BQUHAwEwHQYZYP0OBBYEFEutEJYIKyA8Oe9EC2Mz8pl2ba2PMA4GA1UdDwEB/wQEAwIFIDANBgkq
hkiG9w0BAQUFAAOCAQEANkxAoYGVBx5PLZ6jXW5cob90MrPnUjZRPZBytaagqfR0URHTM2kU/tjS
lv3u6kNRzC5Fe41s3ILO64OKCl2j6GV23w0Ec2IecBVXynCyTxIryRth7a3iVsBPGqYU4P22lHqX
fYPXiKMzUyRN1hnr3J1oFQWkmUe9cPbTDT3ZAaHZrh3Bdv+SXdtyUjXaN2I8ZVl6wcCp0Lq5U0W3
sggd3wNbgWTeNXPgk6n22B1MlCTSDwnn2fokl7ehhmUv+NQ/U4HrODETBa1t3KPVqnWRLkZQiHxo
yHtqBLjdgr6zrU7/yMCB2RoS4blUHqPmPVu0iG7ePTWCfGDvK19npFFofg==
-----END CERTIFICATE-----
```

This command generates a certificate for Windows PowerShell remote management.

## PARAMETERS

### -CN
Specifies an array of common name (CN) values for the **CN** field of remote management certificates.
To connect to the device by using HTTPS, you can use only names that are in the **CN** field of the remote management certificate.
To connect to the device by using HTTP, you can use the IP addresses in addition to CNs.

On the client, you must install the remote management certificate in the trusted root certificate store, and then map each **CN** entry to an IP address of the device.

The device comes preinstalled with a certificate containing the names \<Serial Number\>, \<Serial Number\>Controller0, and \<Serial Number\>Controller1.
\<Serial Number\> is the **SerialNumber** property of the output of the Get-HcsSystem cmdlet.
**SerialNumber** is also the default value of the **CN** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force


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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HcsRemoteManagementCert](./Get-HcsRemoteManagementCert.md)

[Get-HcsSystem](./Get-HcsSystem.md)

