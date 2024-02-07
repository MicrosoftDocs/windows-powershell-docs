---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/secureboot/get-securebootpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SecureBootPolicy
---

# Get-SecureBootPolicy

## SYNOPSIS
Gets the publisher GUID and the policy version of the Secure Boot configuration policy.

## SYNTAX

```
Get-SecureBootPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-SecureBootPolicy** cmdlet gets the publisher GUID and the policy version of the Secure Boot configuration policy.

The cmdlet runs on both UEFI and BIOS (non-UEFI) computers.

If the computer does not support Secure Boot or is a non-UEFI computer, this cmdlet displays the following:

`Secure Boot policy is not enabled on this machine.`

If you do not run Windows PowerShell® in administrator mode, this cmdlet returns an error displaying the following:

`Incorrect authentication data.`

## EXAMPLES

### Example 1: Get Secure Boot policy
```
PS C:\> Get-SecureBootPolicy | Format-List
Publisher: 77fa9abd-0359-4d32-bd60-28f4e78f784b
Version  : 1
```

This command gets the publisher GUID and the policy version of the Secure Boot configuration policy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.SecureBoot.Commands.SecureBootPolicy
This cmdlet returns a **SecureBootPolicy** object that contains the following information about the Secure Boot policy for the computer:

- A GUID named Publisher.
- An unsigned 32-bit integer named Version.

## NOTES

## RELATED LINKS

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)

[Set-SecureBootUEFI](./Set-SecureBootUEFI.md)

