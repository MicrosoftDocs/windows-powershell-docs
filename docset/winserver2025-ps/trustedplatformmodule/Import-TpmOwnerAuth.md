---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/import-tpmownerauth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-TpmOwnerAuth
---

# Import-TpmOwnerAuth

## SYNOPSIS
Imports a TPM owner authorization value to the registry.

## SYNTAX

### File
```
Import-TpmOwnerAuth -File <String> [<CommonParameters>]
```

### Owner Auth
```
Import-TpmOwnerAuth [-OwnerAuthorization] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-TpmOwnerAuth** cmdlet imports a valid Trusted Platform Module (TPM) owner authorization value to the registry.

For more information on TPM, see the [Trusted Platform Module Technology Overview](https://technet.microsoft.com/en-us/library/jj131725.aspx) in the Technet library.

## EXAMPLES

### Example 1: Import an owner authorization value
```
PS C:\> Import-TpmOwnerAuth -OwnerAuthorization "Qn2sdCFQmvjf+tBtSWH4GT87sQs="
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : Qn2sdCFQmvjf+tBtSWH4GT87sQs=
OwnerClearDisabled : True
AutoProvisioning   : DisabledForNextBoot
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command imports the specified owner authorization value to the registry.

### Example 2: Import an owner authorization value from a file
```
PS C:\> Import-TpmOwnerAuth -File "OwnAuthFile.tpm"
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : OwnerClearDisabled : True
AutoProvisioning   : DisabledForNextBoot
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command imports the owner authorization value in the specified file to the registry.

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

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
Specifies the owner authorization value for the TPM.

## OUTPUTS

### TpmObject
This cmdlet returns a **TpmObject** object that contains the following information:

- TpmReady. Whether a TPM complies with Windows Server® 2012 standards.
- TpmPresent. Whether there is a TMP on the current computer.
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is True, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is False, the TPM can be reset through the operating system.
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[ConvertTo-TpmOwnerAuth](./ConvertTo-TpmOwnerAuth.md)

[Set-TpmOwnerAuth](./Set-TpmOwnerAuth.md)

