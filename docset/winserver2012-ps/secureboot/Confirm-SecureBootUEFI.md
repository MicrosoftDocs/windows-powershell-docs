---
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
ms.assetid: 32BF5E0D-3213-4479-9C55-76C94E6051C4
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
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

If the computer supports Secure Boot and Secure Boot is enabled, then this cmdlet returns True.

If the computer supports Secure Boot and Secure Boot is disabled, then this cmdlet returns False.

If the computer does not support Secure Boot or is a BIOS (non-UEFI) computer, then this cmdlet returns an error displaying the following: `Cmdlet not supported on this platform.`

If Windows PowerShell® is not run in administrator mode, then this cmdlet returns an error displaying the following: `Unable to set proper privileges.
Access was denied.`

This cmdlet requires that Windows PowerShell be run in administrator mode.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Confirm-SecureBootUEFI
True
```

This example checks whether or not Secure Boot is enabled on the computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Boolean
If the computer supports Secure Boot and Secure Boot is enabled, then this cmdlet returns True. 

If the computer supports Secure Boot and Secure Boot is disabled, then this cmdlet returns False. 

If the computer does not support Secure Boot or is a BIOS (non-UEFI) computer, then this cmdlet returns an error displaying the following: `Cmdlet not supported on this platform`.

## NOTES

## RELATED LINKS

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)

[Set-SecureBootUEFI](./Set-SecureBootUEFI.md)

