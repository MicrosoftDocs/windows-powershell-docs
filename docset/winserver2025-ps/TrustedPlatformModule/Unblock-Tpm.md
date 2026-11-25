---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/unblock-tpm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-Tpm
---

# Unblock-Tpm

## SYNOPSIS
Resets a TPM lockout.

## SYNTAX

### Owner Auth (Default)
```
Unblock-Tpm [[-OwnerAuthorization] <String>] [<CommonParameters>]
```

### File
```
Unblock-Tpm -File <String> [<CommonParameters>]
```

## DESCRIPTION
The **Unblock-Tpm** cmdlet resets a Trusted Platform Module (TPM) lockout.
TPM locks itself to prevent tampering or attack.
This is called a lockout.
To end a TPM lockout, you must provide a valid owner authorization value.
You can enter an owner authorization value or specify a file that contains the value.
If you do not provide a value, the cmdlet attempts to use a value stored in the registry.

For more information on TPM, see the [Trusted Platform Module Technology Overview](https://technet.microsoft.com/en-us/library/jj131725.aspx) in the Technet library.

## EXAMPLES

### Example 1: Reset a lockout
```
PS C:\>Unblock-Tpm -OwnerAuthorization "vjnuW6rToM41os3xxEpjLdIW2gA="
```

This command resets a TPM lockout.
The command specifies the owner authorization value vjnuW6rToM41os3xxEpjLdIW2gA=.

## PARAMETERS

### -File
Specifies a file that contains the current owner authorization value for the TPM.
You can use the TPM Management Console to create this file.

```yaml
Type: String
Parameter Sets: File
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OwnerAuthorization
Specifies the current owner authorization value for the TPM.

```yaml
Type: String
Parameter Sets: Owner Auth
Aliases: o

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### TpmObject
This cmdlet returns a **TpmObject** object contains the following information:

- TpmReady. Whether a TPM complies with Windows Server® 2012 standards.
- TpmPresent. Whether there is a TMP on the current computer.
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is **True**, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is **False**, the TPM can be reset through the operating system.
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES
* Be sure to understand the protection logic TPM uses. The TPM allows at least one attempt to reset the TPM lockout by using the owner authorization value. For more information, see the [Reset the TPM Lockout](https://technet.microsoft.com/en-us/library/dd851452.aspx) topic in the Technet library.

## RELATED LINKS

[Clear-Tpm](./Clear-Tpm.md)

[Get-Tpm](./Get-Tpm.md)

[Initialize-Tpm](./Initialize-Tpm.md)

