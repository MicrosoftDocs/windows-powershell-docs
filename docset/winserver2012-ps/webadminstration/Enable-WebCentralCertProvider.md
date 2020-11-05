---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: A754C45F-542A-452B-8059-D848E9AE99AE
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Enable-WebCentralCertProvider

## SYNOPSIS
Enables the specified central certificate provider.

## SYNTAX

```
Enable-WebCentralCertProvider -CertStoreLocation <String> -UserName <String> -Password <String>
 [-PrivateKeyPassword <String>] [<CommonParameters>]
```

## DESCRIPTION
Enables a central certificate provider, given its location, private key password, and the credentials of the account that accesses the certificate store.

## EXAMPLES

### Example 1: Enable a central certificate store
```
PS C:\>Enable-WebCentralCertProvider -CertStoreLocation \\MyCertServer\CertStore -UserName CertStoreUser -Password Pa$$w0rd
```

Enables a new central certificate store.

## PARAMETERS

### -CertStoreLocation
Physical path to the central certificate store.
The path is either a local path (for example, `d:\CertStore`) or a UNC path (for example, `\\\\CertStoreServer\CertStore`).

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
Name of the user account that is used to access the central certificate store.

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
Password for the private key if one exists.
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

Required: True
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

