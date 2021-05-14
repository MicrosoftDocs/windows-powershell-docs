---
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/secureboot/get-securebootpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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

The cmdlet will run on both UEFI and BIOS (non-UEFI) computers.

If the computer does not support Secure Boot or is a non-UEFI computer, then this cmdlet returns an error displaying the following: `Secure Boot policy is not enabled on this machine.`

If Windows PowerShell® is not run in administrator mode, then this cmdlet returns an error displaying the following: `Incorrect authentication data.`

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-SecureBootPolicy | Format-List
Publisher: 77fa9abd-0359-4d32-bd60-28f4e78f784b 
Version  : 1
```

This example gets the publisher GUID and the policy version of the Secure Boot configuration policy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.SecureBoot.Commands.SecureBootPolicy
The SecureBootPolicy object contains information about the Secure Boot policy in place for the computer.

Contains the following fields: 

 -- A GUID named publisher. 

 -- An unsigned 32-bit integer named version.

## NOTES

## RELATED LINKS

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)

[Set-SecureBootUEFI](./Set-SecureBootUEFI.md)

