---
external help file: Microsoft.Tpm.Commands.dll-Help.xml
ms.assetid: F9F98617-959C-4C4F-9ED2-4CD25662A493
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Clear-Tpm

## SYNOPSIS
Resets a TPM to its default state.

## SYNTAX

### Owner Auth (Default)
```
Clear-Tpm [[-OwnerAuthorization] <String>] [<CommonParameters>]
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

For more information on TPM, see the Trusted Platform Module Technology Overviewhttp://technet.microsoft.com/en-us/library/jj131725.aspx in the Technet library at http://technet.microsoft.com/en-us/library/jj131725.aspx.

## EXAMPLES

### Example 1: Reset TPM
```
PS C:\> Clear-Tpm


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
```
PS C:\> Clear-Tpm -OwnerAuthorization "vjnuW6rToM41os3xxEpjLdIW2gA="


TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : OwnerClearDisabled : True
AutoProvisioning   : Disabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command resets the TPM by using the specified owner authorization value.

### Example 3: Reset TMP using authorization value from file
```
PS C:\> Clear-Tpm -File "MyOwnerAuthFile.tpm"


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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
The owner authorization value for the TPM.

## OUTPUTS

### TpmObject
A **TpmObject** object contains the following information:

- TpmReady. Whether a TPM complies with Windows Server® 2012 standards.
- TpmPresent. Whether there is a TMP on the current computer.
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is **True**, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is **False**, the TPM can be reset through the operating system. 
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[Get-Tpm](./Get-Tpm.md)

[Initialize-Tpm](./Initialize-Tpm.md)

[Unblock-Tpm](./Unblock-Tpm.md)

