---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/enable-webcentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WebCentralCertProvider
---

# Enable-WebCentralCertProvider

## SYNOPSIS
Enables a central certificate provider.

## SYNTAX

```
Enable-WebCentralCertProvider -CertStoreLocation <String> -UserName <String> -Password <String>
 [-PrivateKeyPassword <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WebCentralCertProvider** cmdlet enables a central certificate provider with the specified location, private key password, and credentials of the account to access the certificate store.

## EXAMPLES

### Example 1: Enable a central certificate store
```
PS C:\> Enable-WebCentralCertProvider -CertStoreLocation "\\MyCertServer\CertStore" -UserName "CertStoreUser" -Password "Pa$$w0rd"
```

This command enables a new central certificate store.

## PARAMETERS

### -CertStoreLocation
Specifies the physical path to the central certificate store.
The path is either a local path such as D:\CertStore, or a UNC path such as \\\\CertStoreServer\CertStore.

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
Specifies the password of the user account that is used to access the central certificate store.

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

### -PrivateKeyPassword
Specifies a password for the private key if one exists.
If specified, this password is the same for all keys.
The password can be $Null.

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

### -UserName
Specifies the name of the user account that is used to access the central certificate store.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

