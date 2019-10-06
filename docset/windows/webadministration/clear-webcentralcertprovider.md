---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Clear-WebCentralCertProvider
ms.reviewer:
ms.assetid: CA1E32A8-6037-4828-984C-0C3A73ED4F3B
---

# Clear-WebCentralCertProvider

## SYNOPSIS
Removes all settings for the central certificate provider.

## SYNTAX

```
Clear-WebCentralCertProvider [-PrivateKeyPassword] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-WebCentralCertProvider** cmdlet removes all settings for the central certificate provider.
The settings that are affected include whether the provider is enabled, the location of the centralized certification store, the user name and password, and the private key password.
This cmdlet does not delete the provider.

## EXAMPLES

### Example 1: Clear certificates
```
PS C:\> Clear-WebCentralCertProvider
```

This command removes all settings for the central certificate provider without removing the provider itself.

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Enable-WebCentralCertProvider](./Enable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

