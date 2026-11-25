---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/set-tpmownerauth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TpmOwnerAuth
---

# Set-TpmOwnerAuth

## SYNOPSIS
Changes the TPM owner authorization value.

## SYNTAX

### NewOwnerAuth File
```
Set-TpmOwnerAuth -File <String> -NewOwnerAuthorization <String> [<CommonParameters>]
```

### NewFile File
```
Set-TpmOwnerAuth -File <String> -NewFile <String> [<CommonParameters>]
```

### NewFile OwnerAuth
```
Set-TpmOwnerAuth [[-OwnerAuthorization] <String>] -NewFile <String> [<CommonParameters>]
```

### NewOwnerAuth OwnerAuth
```
Set-TpmOwnerAuth [[-OwnerAuthorization] <String>] -NewOwnerAuthorization <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-TpmOwnerAuth** cmdlet changes the current owner authorization value of the Trusted Platform Module (TPM) to a new value.
You can specify the current owner authorization value or specify a file that contains the current owner authorization value.
If you do not specify an owner authorization value, the cmdlet attempts to read the value from the registry.

Use the ConvertTo-TpmOwnerAuth cmdlet to create an owner authorization value.
You can specify a new owner authorization value or specify a file that contains the new value.

An owner authorization file is not a simply a password.
It is generated for a specific system.
For more information on TPM, see the [Trusted Platform Module Technology Overview](https://technet.microsoft.com/en-us/library/jj131725.aspx) in the Technet library.

## EXAMPLES

### Example 1: Replace imported owner authorization value
```
PS C:\> Set-TpmOwnerAuth -NewOwnerAuthorization "h4FCmNeWVNp5IMHxRfFL9QEq4vM="
TpmReady           : True
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : h4FCmNeWVNp5IMHxRfFL9QEq4vM=
OwnerClearDisabled : True
AutoProvisioning   : DisabledForNextBoot
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command replaces the current owner authorization value with the specified owner authorization value.
The command does not specify the current owner authorization value, so the cmdlet attempts to find it in the registry.
This command does not import the owner authorization value into the registry.
After you run this command, you can use the Import-TpmOwnerAuth cmdlet to import the new value into the registry, if necessary.

### Example 2: Replace owner authorization value with value in file
```
PS C:\> Set-TpmOwnerAuth -NewFile "NewOwnerAuth.tpm"
TpmReady           : True
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : h4FCmNeWVNp5IMHxRfFL9QEq4vM=
OwnerClearDisabled : True
AutoProvisioning   : DisabledForNextBoot
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command replaces the current owner authorization value with the owner authorization value in the specified file.

### Example 3: Replace owner authorization value
```
PS C:\> Set-TpmOwnerAuth -OwnerAuthorization "oaVq17hNcFS2KSnHwpZa4AlrWBo=" -NewOwnerAuthorization "h4FCmNeWVNp5IMHxRfFL9QEq4vM="
TpmReady           : True
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : h4FCmNeWVNp5IMHxRfFL9QEq4vM=
OwnerClearDisabled : True
AutoProvisioning   : DisabledForNextBoot
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command replaces the specified owner authorization value with a new owner authorization value.

## PARAMETERS

### -File
Specifies a file that contains the current owner authorization value for the TPM.
You can use the TPM Management Console to create this file.

```yaml
Type: String
Parameter Sets: NewOwnerAuth File, NewFile File
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFile
Specifies a file that contains the new owner authorization value for a TPM.

```yaml
Type: String
Parameter Sets: NewFile File, NewFile OwnerAuth
Aliases: nf

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewOwnerAuthorization
Specifies a new owner authorization value for a TPM.

```yaml
Type: String
Parameter Sets: NewOwnerAuth File, NewOwnerAuth OwnerAuth
Aliases: no

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OwnerAuthorization
Specifies the current owner authorization value for a TPM.

```yaml
Type: String
Parameter Sets: NewFile OwnerAuth, NewOwnerAuth OwnerAuth
Aliases: o

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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
- TpmPresent. Whether there is a TMP on the current computer.
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is True, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is False, the TPM can be reset through the operating system.
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[ConvertTo-TpmOwnerAuth](./ConvertTo-TpmOwnerAuth.md)

[Import-TpmOwnerAuth](./Import-TpmOwnerAuth.md)

