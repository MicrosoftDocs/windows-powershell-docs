---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDCertificate
---

# Get-RDCertificate

## SYNOPSIS
Gets certificates associated with RDS roles.

## SYNTAX

```
Get-RDCertificate [[-Role] <RDCertificateRole>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDCertificate** cmdlet gets certificates associated with Remote Desktop Services (RDS) roles.

This cmdlet modifies an object that contains the following information:

- Subject.
The subject of the certificate.
- SubjectAlternateName.
A list of subject alternative name entries of the certificate.
- IssuedBy.
Common name of the issuer of the certificate.
- IssuedTo.
Common name of the IssuedTo field of the certificate.
- ExpiresOn.
Expiration date of the certificate.
- Thumbprint.
Thumbprint of the certificate.
- Role.
Remote desktop role service name.
The possible roles are: RDGateway, RDWebAccess, RDRedirector, and RDPublishing.
- Level.
Certification level.

The certification levels are:

- Not Configured.
The role service is not configured with a certificate or the certificate is not valid.
- Untrusted.
The role service is configured with a self-signed certificate.
- Trusted.
The role service is configured with either enterprise certificate or public certificate.

## EXAMPLES

### Example 1: Get certificates for an RD Connection Broker
```
PS C:\> Get-RDCertificate -ConnectionBroker "RDConnectionBroker.Contoso.com"
```

This command gets certificates for server roles for the RD Connection Broker server named RDConnectionBroker.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Role
Specifies a certificate type associated with an RDS server role.
The acceptable values for this parameter are:

- RDGateway
- RDWebAccess
- RDRedirector
- RDPublishing

```yaml
Type: RDCertificateRole
Parameter Sets: (All)
Aliases:
Accepted values: RDGateway, RDWebAccess, RDRedirector, RDPublishing

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-RDCertificate](./New-RDCertificate.md)

[Set-RDCertificate](./Set-RDCertificate.md)

