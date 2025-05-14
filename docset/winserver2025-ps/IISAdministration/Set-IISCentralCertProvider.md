---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/set-iiscentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IISCentralCertProvider
---

# Set-IISCentralCertProvider

## SYNOPSIS
Sets property values for the IIS central certificate store.

## SYNTAX

```
Set-IISCentralCertProvider [-CertStoreLocation <String>] [-UserName <String>] [-Password <SecureString>]
 [-PrivateKeyPassword <SecureString>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IISCentralCertProvider** cmdlet modifies property values for the IIS central certificate store.
The central certificate store allows you to store all your IIS certificates in a centralized location (such as a file store); IIS servers then retrieve certificate information from this centralized location.
That means that you only have to install certificates in one location; there is no need to install the same certificate on each and every IIS server.

**Set-IISCentralCertProvider** is typically used in one of two scenarios: 1) if you need to change the physical location of the certificate store (for example, if you have moved the store to a new file share); or, 2) if you have run the **Clear-IISCentralCertProvider** cmdlet and have erased all the certificate store property values.
These values must be reconfigured before you can take advantage of the central store capabilities.

## EXAMPLES

### Example 1: Modify the location of the central certificate store
```
PS C:\> Set-IISCentralCertProvider -CertStoreLocation "\\NewCertStoreServer\CertStore"
```

This command modifies the location of the IIS central certificate store.
In this example, the store has been moved to the file share \\\\NewCertStoreServer\CertStore.
Note that **Set-IISCentralCertProvider** does not move the certificate files to the new location.
Instead, the cmdlet merely configures the certificate store to use this new location.

## PARAMETERS

### -CertStoreLocation
Specifies the physical path to the central certificate store; this can be either a local path (e.g., D:\CertStore) or a UNC path.
For example:

`-CertStoreLocation "\\\\CertStoreServer\CertStore"`

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

### -Password
Specifies the password for the user account used to access the certificate store.
For example:

`-Password "P@ssw0rd"`

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
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

Required: False
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
The central store user account can be either a local account or a domain account.

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

[Enable-IISCentralCertProvider](./Enable-IISCentralCertProvider.md)

[Get-IISCentralCertProvider](./Get-IISCentralCertProvider.md)

[Set-IISCentralCertProviderCredential](./Set-IISCentralCertProviderCredential.md)

