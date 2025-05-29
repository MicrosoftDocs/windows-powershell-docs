---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
Module Name: KDS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/kds/get-kdsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-KdsConfiguration
---

# Get-KdsConfiguration

## SYNOPSIS
Retrieves the current configuration of the Microsoft Group KdsSvc from Active Directory.

## SYNTAX

```
Get-KdsConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-KdsConfiguration** cmdlet retrieves the current configuration of the Microsoft Group Key Distribution Service (KdsSvc) from Active Directory.
The KDS configuration defines how keys are generated from the root keys.

## EXAMPLES

### Example 1: Retrieve the current KDS configuration
```
PS C:\> Get-KdsConfiguration
```

This command retrieves the current configuration of the Microsoft Group KdsSvc from Active Directory.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.KeyDistributionService.KdsServerConfiguration
This cmdlet returns a **KdsServerConfiguration** object contains information such as the key derivation function (KDF) algorithm and secret agreement algorithm used in key generation.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsRootKey](./Get-KdsRootKey.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

