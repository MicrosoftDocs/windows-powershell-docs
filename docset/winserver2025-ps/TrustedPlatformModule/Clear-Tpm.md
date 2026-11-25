---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/clear-tpm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Tpm
---

# Clear-Tpm

## SYNOPSIS
Resets a TPM to its default state.

## SYNTAX

### Owner Auth (Default)
```
Clear-Tpm [-UsePPI] [[-OwnerAuthorization] <String>] [<CommonParameters>]
```

### File
```
Clear-Tpm -File <String> [<CommonParameters>]
```

## DESCRIPTION
The **Clear-Tpm** cmdlet resets the Trusted Platform Module (TPM) to its default state.
A reset removes the owner authorization value and any keys stored in the TPM.
To reset a TPM, you must provide a valid owner authorization value.
You can enter an owner authorization value or specify a file that contains the value.
If you do not provide a value, the cmdlet attempts to use a value stored in the registry.

For more information on TPM, see the [Trusted Platform Module Technology Overview](https://technet.microsoft.com/en-us/library/jj131725.aspx) in the TechNet library.

## EXAMPLES

### Example 1: Reset TPM
```powershell
Clear-Tpm
```
```output
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          :
OwnerClearDisabled : True
AutoProvisioning   : Disabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command resets the TPM.
The command uses the owner authorization value stored in the registry instead of specifying a value or using a value in a file.

### Example 2: Reset TPM with a supplied authorization value
```powershell
Clear-Tpm -OwnerAuthorization "vjnuW6rToM41os3xxEpjLdIW2gA="
```
```output
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          :
OwnerClearDisabled : True
AutoProvisioning   : Disabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command resets the TPM by using the specified owner authorization value.

### Example 3: Reset TPM using authorization value from file
```powershell
Clear-Tpm -File "MyOwnerAuthFile.tpm"
```
```output
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          :
OwnerClearDisabled : True
AutoProvisioning   : Disabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command resets the TPM by using the owner authorization value included in the specified file.

### Example 4: Reset TPM with Physical Presence Interface
```powershell
Clear-Tpm -UsePPI
```
```output
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          :
OwnerClearDisabled : True
AutoProvisioning   : Disabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command resets the TPM by using the Physical Presence Interface (PPI).
The PPI does not use a value for owner authorization.

Restart the system for the clear action to take effect.
The restart might require user input to approve the clear request.

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

### -UsePPI
Use the PPI for the TPM reset.
Restart the system for the changes to take effect.
The restart might require user input to approve the clear request.

```yaml
Type: SwitchParameter
Parameter Sets: Owner Auth
Aliases: ppi

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
This cmdlet accepts the owner authorization value for the TPM.

## OUTPUTS

### TpmObject
This cmdlet returns a **TpmObject** object contains the following information:

- TpmReady. Whether a TPM complies with Windows Server® 2012 standards.
- TpmPresent. Whether there is a TPM on the current computer.
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is True, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is False, the TPM can be reset through the operating system.
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[Get-Tpm](./Get-Tpm.md)

[Initialize-Tpm](./Initialize-Tpm.md)

[Unblock-Tpm](./Unblock-Tpm.md)

