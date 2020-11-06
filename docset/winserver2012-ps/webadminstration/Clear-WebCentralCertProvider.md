---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: CA1E32A8-6037-4828-984C-0C3A73ED4F3B
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Clear-WebCentralCertProvider

## SYNOPSIS
Removes all settings for the central certificate provider.

## SYNTAX

```
Clear-WebCentralCertProvider [-PrivateKeyPassword] [<CommonParameters>]
```

## DESCRIPTION
Removes all settings for the central certificate provider.
The settings that are affected include: whether the provider is enabled, the location of the centralized certification store, user name and password, and the private key password.
This command does not delete the provider.

## EXAMPLES

### Example 1: Clear certificates
```
Removes all settings for the central certificate provider without removing the provider itself.
PS C:\>Clear-WebCentralCertProvider
```

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

