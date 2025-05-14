---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/set-webcentralcertprovidercredential?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebCentralCertProviderCredential
---

# Set-WebCentralCertProviderCredential

## SYNOPSIS
Changes the user-account credentials for the central certificate provider.

## SYNTAX

```
Set-WebCentralCertProviderCredential [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebCentralCertProviderCredential** cmdlet changes the user-account credentials (user name and password) for the central certificate provider.

## EXAMPLES

### Example 1: Set credentials
```
PS C:\> Set-WebCentralCertProviderCredentials -UserName "CertStoreUser"
UserName=CertStoreUser

Password=

*********

Confirm Password=

*********
```

This command changes the user-account credentials for the central certificate store.

## PARAMETERS

### -UserName
Specifies the password of the user account that is used to access the central certificate store.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

