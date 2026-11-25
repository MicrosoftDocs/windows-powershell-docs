---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/set-iiscentralcertprovidercredential?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IISCentralCertProviderCredential
---

# Set-IISCentralCertProviderCredential

## SYNOPSIS
Modifies the user account credentials for the IIS certificate store.

## SYNTAX

```
Set-IISCentralCertProviderCredential [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-IISCentralCertProviderCredential** cmdlet enables you to change the user account used to access the IIS central certificate store.
The central certificate store allows you to store all your IIS certificates in a centralized location (such as a file share); IIS servers then retrieve certificate from this centralized location.
That means that you only have to install certificates in one location; there is no need to install the same certificate on each and every IIS server.

Servers access the central store by using a preconfigured user account.
This account, which can be either a local account or a domain account, must have read-only access to the certificate store location.
You must specify a user account when you initially enable the certificate store.
However, you can change this user account at any time by running **Set-IISCentralCertProviderCredential**.

## EXAMPLES

### Example 1
```
PS C:\> Set-IISCentralCertProviderCredential -UserName "IISCertificateAdmin"
```

This command changes the central certificate store user account to IISCertificateAdmin.
Note that you only specify the user name when calling **Set-IISCentralCertProviderCredential**.
When the command runs you will be prompted to enter the password for the specified user account.

## PARAMETERS

### -UserName
Specifies the user account used to access the certificate store; this can be either an Active Directory SAM Account Name or a user principal name.
For example:

-UserName "IISCertificateAdmin"

It is recommended that you create a user account reserved solely for certificate administration, and that you give this account only the privileges required to manage the certificate store (most notably, the account needs read access to the store location).
The central store user account can be either a local account or a domain account.

Note that you only need to specify the user account name.
You will be prompted for the user account password when the command actually runs.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### String

## NOTES

## RELATED LINKS

[Clear-IISCentralCertProvider](./Clear-IISCentralCertProvider.md)

[Disable-IISCentralCertProvider](./Disable-IISCentralCertProvider.md)

[Enable-IISCentralCertProvider](./Enable-IISCentralCertProvider.md)

[Get-IISCentralCertProvider](./Get-IISCentralCertProvider.md)

[Set-IISCentralCertProvider](./Set-IISCentralCertProvider.md)

