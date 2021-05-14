---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfssslcertificate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsSslCertificate
---

# Get-AdfsSslCertificate

## SYNOPSIS
Gets the host name, port, and certificate hash for SSL bindings configured for AD FS and the device registration service.

## SYNTAX

```
Get-AdfsSslCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsSslCertificate** cmdlet gets the host name, port, and certificate hash for all SSL bindings configured for Active Directory Federation Services (AD FS) and, if enabled, the device registration service.

## EXAMPLES

### Example 1: Get information for SSL bindingscertificate hashesinformation for SSL bindings
```
PS C:\> Get-AdfsSslCertificate
HostName                           PortNumber  CertificateHash
--------                           ----------  ---------------
sts.contoso100.com                    443      4195EE03C2721F7478B67E94BD83BB373FE22D98
localhost                             443      4195EE03C2721F7478B67E94BD83BB373FE22D98
sts.contoso100.com                   49443     4195EE03C2721F7478B67E94BD83BB373FE22D98
EnterpriseRegistration.contoso...     443      4195EE03C2721F7478B67E94BD83BB373FE22D98
```

This command gets the host names, ports, and certificate hashes for all configured SSL bindings.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AdfsSslCertificate](./Set-AdfsSslCertificate.md)

