---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Confirm-SecureBootUEFI
ms.reviewer:
ms.assetid: 32BF5E0D-3213-4479-9C55-76C94E6051C4
---

# Confirm-SecureBootUEFI

## SYNOPSIS
Confirms that Secure Boot is enabled by checking the Secure Boot status on the local computer.

## SYNTAX

```
Confirm-SecureBootUEFI [<CommonParameters>]
```

## DESCRIPTION
The **Confirm-SecureBootUEFI** cmdlet confirms that Secure Boot is enabled by checking the Secure Boot status on a UEFI computer.

If the computer supports Secure Boot and Secure Boot is enabled, this cmdlet returns $True.

If the computer supports Secure Boot and Secure Boot is disabled, this cmdlet returns $False.

If the computer does not support Secure Boot or is a BIOS (non-UEFI) computer, this cmdlet displays the following: 

`Cmdlet not supported on this platform.`

If Windows PowerShell® is not run in administrator mode, this cmdlet displays the following: 

`Unable to set proper privileges.
Access was denied.`

This cmdlet requires that Windows PowerShell be run in administrator mode.

## EXAMPLES

### Example 1: Confirm Secure Boot
```
PS C:\> Confirm-SecureBootUEFI
True
```

This command checks whether Secure Boot is enabled on the computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Boolean
This cmdlet returns a Boolean.
If the computer supports Secure Boot and Secure Boot is enabled, this cmdlet returns $True.

If the computer supports Secure Boot and Secure Boot is disabled, this cmdlet returns $False.

If the computer does not support Secure Boot or is a BIOS (non-UEFI) computer, this cmdlet displays the following: 

`Cmdlet not supported on this platform`.

## NOTES

## RELATED LINKS

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)

[Set-SecureBootUEFI](./Set-SecureBootUEFI.md)

