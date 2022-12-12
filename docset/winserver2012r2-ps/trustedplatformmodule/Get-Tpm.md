---
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/get-tpm?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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

For more information on TPM, see the Trusted Platform Module Technology Overviewhttp://technet.microsoft.com/en-us/library/jj131725.aspx in the Technet library at http://technet.microsoft.com/en-us/library/jj131725.aspx.

## EXAMPLES

### Example 1: Display TPM information
```
PS C:\> Get-Tpm


TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          :
OwnerClearDisabled : True
AutoProvisioning   : Enabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command displays information about the TPM of the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### TpmObject
A **TpmObject** object contains the following information:

- TpmReady. Whether a TPM complies with Windows Server® 2012 standards.
- TpmPresent. Whether there is a TPM on the current computer
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is **True**, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is **False**, the TPM can be reset through the operating system. 
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[Clear-Tpm](./Clear-Tpm.md)

[Initialize-Tpm](./Initialize-Tpm.md)

[Unblock-Tpm](./Unblock-Tpm.md)

