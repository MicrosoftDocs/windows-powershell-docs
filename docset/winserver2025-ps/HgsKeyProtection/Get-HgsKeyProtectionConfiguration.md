---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/get-hgskeyprotectionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HgsKeyProtectionConfiguration
---

# Get-HgsKeyProtectionConfiguration

## SYNOPSIS
Gets the configuration of the Key Protection Service.

## SYNTAX

```
Get-HgsKeyProtectionConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsKeyProtectionConfiguration** cmdlet gets the configuration of the Key Protection Service that runs on the local computer.
The configuration contains the communication certificate that the Key Protection Service uses to sign the metadata provided by the service.

## EXAMPLES

### Example 1: Get the configuration of the Key Protection Service
```
PS C:\> Get-HgsKeyProtectionConfiguration
```

This command gets the configuration of the Key Protection Service on the local computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.Windows.KpsServer.Common.Store.Data.ServiceConfiguration
This cmdlet returns the configuration of Key Protection Service set up on the local computer.

## NOTES

## RELATED LINKS

[Set-HgsKeyProtectionConfiguration](./Set-HgsKeyProtectionConfiguration.md)

