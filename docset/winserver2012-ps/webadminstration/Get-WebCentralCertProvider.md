---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: E3026A42-359B-4BEE-BC2F-8DF3B9DC5329
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
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
Retrieves the configuration settings of the central certificate provider.
The settings that you can retrieve include: whether the provider is enabled, the location of the centralized certification store, user name, and the private key password.

## EXAMPLES

### Example 1: Retrieve all settings
```
PS C:\>Get-WebCentralCertProvider
Enabled=True

CertStoreLocation=\\MyCertServer\CertStore

UserName=CertStoreUser

Password=*********

PrivateKeyPassword=
```

Retrieves all configuration settings of the central certificate provider.

### Example 2: Retrieve location of the central certificate store
```
PS C:\>Get-WebCentralCertProvider -CertStoreLocation
CertStoreLocation=\\MyCertServer\CertStore
```

Retrieves the location of the central certificate store from the provider.

## PARAMETERS

### -CertStoreLocation
Physical path to the central certificate store.
The path is either a local path (for example, `d:\CertStore`) or a UNC path (for example, `\\\\CertStoreServer\CertStore`).

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
If the central certificate provider is enabled, this parameter returns True; otherwise, it returns False.

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
Password for the private key if one exists.
If provided, this password is the same for all keys.
The password can be $null.

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
Name of the user account that is used to access the central certificate store.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

