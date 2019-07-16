---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: CE40617B-880D-4566-B0BC-CAFA0601BE89
manager: dansimp
ms.mktglfcycl: manage
ms.date: 12/20/2016
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Clear-IISCentralCertProvider
ms.author: v-anbarr
ms.reviewer:
---

# Clear-IISCentralCertProvider

## SYNOPSIS
Removes configuration information from the IIS central certificate store.

## SYNTAX

```
Clear-IISCentralCertProvider [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-IISCentralCertProvider** cmdlet removes all settings for the central certificate provider.
You must specify the *Force* parameter if the Central Certificate Store feature is enabled.
If you specify *Force*, the feature is disabled and all the settings are cleared.
If the Central Certificate Store feature is already disabled, you do not need to specify *Force*.

## EXAMPLES

### Example 1: Clear configuration information from the IIS certificate store
```
PS C:\> Clear-IISCentralCertProvider
```

This command removes all the configuration information for the IIS central certificate store without removing the provider itself.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-IISCentralCertProvider](./Disable-IISCentralCertProvider.md)

[Enable-IISCentralCertProvider](./Enable-IISCentralCertProvider.md)

[Get-IISCentralCertProvider](./Get-IISCentralCertProvider.md)

[Set-IISCentralCertProvider](./Set-IISCentralCertProvider.md)

[Set-IISCentralCertProviderCredential](./Set-IISCentralCertProviderCredential.md)

