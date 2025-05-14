---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/get-tpm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Tpm
---

# Get-Tpm

## SYNOPSIS
Gets an object that contains information about a TPM.

## SYNTAX

```
Get-Tpm [<CommonParameters>]
```

## DESCRIPTION
The **Get-Tpm** cmdlet gets a **TpmObject**.
This object contains information about the Trusted Platform Module (TPM) on the current computer.

For more information on TPM, see the [Trusted Platform Module Technology Overview](https://technet.microsoft.com/en-us/library/jj131725.aspx) in the Technet library.

## EXAMPLES

### Example 1: Display TPM information
```
PS C:\> Get-Tpm
```
```output
TpmPresent                : True
TpmReady                  : True
TpmEnabled                : True
TpmActivated              : True
TpmOwned                  : True
RestartPending            : True
ManufacturerId            : 1229870147
ManufacturerIdTxt         : INTC
ManufacturerVersion       : 402.1.0.0
ManufacturerVersionFull20 : 402.1.0.0

ManagedAuthLevel          : Full
OwnerAuth                 :
OwnerClearDisabled        : False
AutoProvisioning          : Enabled
LockedOut                 : False
LockoutHealTime           : 10 minutes
LockoutCount              : 0
LockoutMax                : 31
SelfTest                  : {}
```

This command displays information about the TPM of the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### TpmObject
This cmdlet returns a **TpmObject** object that contains the following information:

- TpmReady. Whether a TPM complies with Windows Server 2012 standards.
- TpmPresent. Whether there is a TPM on the current computer
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerAuth. Current owner authorization value of the Trusted Platform Module (TPM).
- OwnerClearDisabled. Whether TPM can be reset. If this value is True, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is False, the TPM can be reset through the operating system.
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- LockoutHealTime. The time that has to pass until you can unlock the TPM.
- LockoutCount. Number of failed attempts.
- LockoutMax. Limit of failed attempts.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[Clear-Tpm](./Clear-Tpm.md)

[Initialize-Tpm](./Initialize-Tpm.md)

[Unblock-Tpm](./Unblock-Tpm.md)

