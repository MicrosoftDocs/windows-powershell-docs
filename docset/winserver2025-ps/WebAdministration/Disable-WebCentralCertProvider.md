---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/disable-webcentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WebCentralCertProvider
---

# Disable-WebCentralCertProvider

## SYNOPSIS
Takes the central certificate provider offline.

## SYNTAX

```
Disable-WebCentralCertProvider [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WebCentralCertProvider** cmdlet takes the central certificate provider offline.
Use the [Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md) cmdlet to re-enable the provider.

## EXAMPLES

### Example 1: Disable the central certificate provider
```
PS C:\> Disable-WebCentralCertProvider
```

This command takes the central certificate provider offline.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Enable-WebCentralCertProvider](./Enable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)

