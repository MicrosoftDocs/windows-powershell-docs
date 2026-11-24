---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webcentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebCentralCertProvider
---

# Get-WebCentralCertProvider

## SYNOPSIS
Retrieves the configuration settings of the central certificate provider.

## SYNTAX

```
Get-WebCentralCertProvider [-CertStoreLocation] [-UserName] [-PrivateKeyPassword] [-Enabled]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebCentralCertProvider** cmdlet retrieves the configuration settings of the central certificate provider.
The settings that you can retrieve include whether the provider is enabled, the location of the centralized certification store, the user name, and the private key password.

## EXAMPLES

### Example 1: Retrieve all settings
```
PS C:\> Get-WebCentralCertProvider
Enabled=True

CertStoreLocation=\\MyCertServer\CertStore

UserName=CertStoreUser

Password=*********

PrivateKeyPassword=
```

This command retrieves all configuration settings of the central certificate provider.

### Example 2: Retrieve the location of the central certificate storethe
```
PS C:\> Get-WebCentralCertProvider -CertStoreLocation
CertStoreLocation=\\MyCertServer\CertStore
```

This command retrieves the location of the central certificate store from the provider.

## PARAMETERS

### -CertStoreLocation
Indicates that this cmdlet gets the physical path to the central certificate store.
The path is either a local path such as D:\CertStore, or a UNC path such as \\\\CertStoreServer\CertStore.

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

### -Enabled
Indicates whether the central certificate provider is enabled, which returns $True; otherwise, this parameter returns $False.

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

### -PrivateKeyPassword
Indicates the password for the private key if one exists.
If specified, this password is the same for all keys.
The password can be $Null.

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

### -UserName
Indicates the name of the user account that is used to access the central certificate store.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Enable-WebCentralCertProvider](./Enable-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

