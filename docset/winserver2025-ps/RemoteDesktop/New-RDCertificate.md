---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/new-rdcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDCertificate
---

# New-RDCertificate

## SYNOPSIS
Creates a certificate for an RDS role.

## SYNTAX

```
New-RDCertificate [-Role] <RDCertificateRole> -DnsName <String> [-ExportPath <String>] -Password <SecureString>
 [-ConnectionBroker <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-RDCertificate** cmdlet creates a certificate for a Remote Desktop Services (RDS) role.

This cmdlet creates an object that contains the following information:

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

### Example 1: Create a certificate
```
PS C:\> $Password = ConvertTo-SecureString -String "Wings%%83Potato" -AsPlainText -Force
PS C:\> New-RDCertificate -Role RDPublishing -DnsName "RDWA01.Contoso.com " -Password $Password -ConnectionBroker "RDCB.Contoso.com"
```

This example creates a certificate for an RDS role.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string based on a string that the user supplies, and stores it in the **$Password** variable.
For more information, type `Get-Help ConvertTo-SecureString`.

The second command creates a certificate for the publishing role and uses the secure string stored in **$Password** to help secure it.
The command specifies the DNS name of the RDS host and the name of the connection broker.

### Example 2: Create and export a certificate
```
PS C:\> $Password = ConvertTo-SecureString -String "Cups34Horses&&" -AsPlainText -Force
PS C:\> New-RDCertificate -Role RDWebAccess -DnsName "RDWA01.Contoso.com" -Password $Password -ExportPath "C:\Certificates\RDWA102.pfx" -ConnectionBroker "RDCB.Contoso.com"
```

This example creates a certificate for an RDS role and exports it to a specified file.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string based on a string that the user supplies, and stores it in the **$Password** variable.

The second command creates a certificate for the web access role and uses the secure string stored in **$Password** to help secure it.
The command specifies the DNS name of the RDS host and the name of the connection broker.
This command also exports the certificate to the specified .pfx file.

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

### -DnsName
Specifies the Domain Name Service (DNS) name for a computer.
The cmdlet creates a self-signed certificate for this computer.

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

### -ExportPath
Specifies a full file path for the certificate.
The file has a .pfx extension.

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

### -Password
Specifies a secure string used to help secure the certificate.
See the Examples section.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: True
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

Required: True
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

[Get-RDCertificate](./Get-RDCertificate.md)

[Set-RDCertificate](./Set-RDCertificate.md)

