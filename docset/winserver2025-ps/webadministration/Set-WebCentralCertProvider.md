---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/set-webcentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebCentralCertProvider
---

# Set-WebCentralCertProvider

## SYNOPSIS
Changes the configuration settings for the central certificate provider.

## SYNTAX

```
Set-WebCentralCertProvider [-CertStoreLocation <String>] [-UserName <String>] [-Password <String>]
 [-PrivateKeyPassword <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebCentralCertProvider** cmdlet changes the configuration settings for the central certificate provider.
The settings that you can set include whether the provider is enabled, the location of the centralized certification store, the user name and password, and the private key password.

## EXAMPLES

### Example 1: Set the central certificate store location
```
PS C:\> Set-WebCentralCertProvider -CertStoreLocation "\\MyCertServer\CertStore"
```

This command sets the physical location of the central certificate store.

## PARAMETERS

### -CertStoreLocation
Specifies the physical path to the central certificate store.
The path is either a local path such as D:\CertStore, or a UNC path such as \\\\MyCertServer\CertStore.

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
Specifies the password for the user account that is used to access the central certificate store.

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

### -PrivateKeyPassword
Specifies the password for the private key.
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

Required: False
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

[Enable-WebCentralCertProvider](./Enable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

