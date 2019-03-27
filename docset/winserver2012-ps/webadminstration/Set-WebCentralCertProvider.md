---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: B7B5E253-C341-4F24-81FE-A024D7CBC8A7
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-WebCentralCertProvider

## SYNOPSIS
Sets the configuration settings for the central certificate provider.

## SYNTAX

```
Set-WebCentralCertProvider [-CertStoreLocation <String>] [-UserName <String>] [-Password <String>]
 [-PrivateKeyPassword <String>] [<CommonParameters>]
```

## DESCRIPTION
Sets the configuration settings for the central certificate provider.
The settings that you can set include: whether the provider is enabled, the location of the centralized certification store, user name and password, and the private key password.

## EXAMPLES

### Example 1: Set the central certificate store location
```
PS C:\>Set-WebCentralCertProvider -CertStoreLocation \\MyCertServer\CertStore
```

Sets the physical location of the central certificate store.

## PARAMETERS

### -CertStoreLocation
Physical path to the central certificate store.
The path is either a local path (for example, `d:\CertStore`) or a UNC path (for example, `\\\\MyCertServer\CertStore`).

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
Password for the user account that is used to access the central certificate store.

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
Password for the private key.
If provided, this password is the same for all keys.
The password can be $null.

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
Name of the user account that is used to access the central certificate store.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProviderCredential](./Set-WebCentralCertProviderCredential.md)

