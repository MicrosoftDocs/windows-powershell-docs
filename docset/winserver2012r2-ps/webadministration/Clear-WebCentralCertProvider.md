---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Clear-WebCentralCertProvider
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CA1E32A8-6037-4828-984C-0C3A73ED4F3B
ms.author: v-kaunu
ms.reviewer: brianlic
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
PS C:\>Clear-WebCentralCertProvider
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Enable-WebCentralCertProvider](./Enable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

