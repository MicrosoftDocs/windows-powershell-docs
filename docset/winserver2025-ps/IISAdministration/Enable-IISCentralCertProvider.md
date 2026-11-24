---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/enable-iiscentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-IISCentralCertProvider
---

# Enable-IISCentralCertProvider

## SYNOPSIS
Enables the IIS central certificate store.

## SYNTAX

```
Enable-IISCentralCertProvider -CertStoreLocation <String> -UserName <String> -Password <SecureString>
 -PrivateKeyPassword <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-IISCentralCertProvider** cmdlet enables the IIS central certificate store.
The central certificate store allows you to store all your IIS certificates in a centralized location (such as a file share); IIS servers then retrieve certificate from this centralized location.
That means that you only have to install certificates in one location; there is no need to install the same certificate on each and every IIS server.

When you install the central certificate store the store is disabled by default.
To actually use this capability you need to run the **Enable-IISCentralCertProvider** cmdlet.

## EXAMPLES

### Example 1: Enable the central certificate store
```
PS C:\> Enable-IISCentralCertProvider -CertStoreLocation "\\CertStoreServer\CertStore" -UserName "IISCertificateAdmin" -Password "P@ssw0rd"
```

This command enables the IIS central certificate store.
In this example, the certificate store is located on file share \\\\CertStoreServer\CertStore and accessed by using the user account IISCertificateAdmin.

### Example 2: Enable the central certificate store and specify the private key password
```
PS C:\> Enable-IISCentralCertProvider -CertStoreLocation "\\CertStoreServer\CertStore" -UserName "IISCertificateAdmin" -Password "P@ssw0rd" -PrivateKeyPassword "pa$$W0rd"
```

This command is a variation of the command shown in Example 1.
In Example 2, however, the *PrivateKeyPassword* parameter is included to specify the private key password that has been assigned to all the IIS certificates.

## PARAMETERS

### -CertStoreLocation
Specifies the physical path to the central certificate store; this can be either a local path (e.g., D:\CertStore) or a UNC path.
For example:

`-CertStoreLocation "\\\\CertStoreServer\CertStore"`

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

### -Password
Specifies the password for the user account used to access the certificate store.
For example:

`-Password "P@ssw0rd"`

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateKeyPassword
Specifies the private key password for your IIS certificates.
For example:

`-PrivateKeyPassword "pa$$W0rd"`

This parameter should only be used if all your IIS certificates share the same password.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies the user account used to access the certificate store; this can be either an Active Directory SAM Account Name or a user principal name.
For example:

`-UserName "IISCertificateAdmin"`

It is recommended that you create a user account reserved solely for certificate administration, and that you give this account only the privileges required to manage the certificate store (most notably, the account needs read access to the store location).
The certificate store user account can be either a local account or a domain account.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Security.SecureString

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-IISCentralCertProvider](./Clear-IISCentralCertProvider.md)

[Disable-IISCentralCertProvider](./Disable-IISCentralCertProvider.md)

[Get-IISCentralCertProvider](./Get-IISCentralCertProvider.md)

[Set-IISCentralCertProvider](./Set-IISCentralCertProvider.md)

[Set-IISCentralCertProviderCredential](./Set-IISCentralCertProviderCredential.md)

