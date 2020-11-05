---
external help file: Microsoft.Tpm.Commands.dll-Help.xml
ms.assetid: 00BC67FE-0042-4424-AC02-DD8843D82D96
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Initialize-Tpm

## SYNOPSIS
Performs part of the provisioning process for a TPM.

## SYNTAX

```
Initialize-Tpm [-AllowClear] [-AllowPhysicalPresence] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-Tpm** cmdlet performs part of the provisioning process for a Trusted Platform Module (TPM).
Provisioning is the process of preparing a TPM to be used.
You may need to perform other steps to fully provision a TPM.

For more information on TPM, see the Trusted Platform Module Technology Overviewhttp://technet.microsoft.com/en-us/library/jj131725.aspx in the Technet library at http://technet.microsoft.com/en-us/library/jj131725.aspx.

## EXAMPLES

### Example 1: Initialize a TPM
```
PS C:\> Initialize-Tpm -ForceClearAllowed -PhysicalPresenceAllowed


TpmReady                 : False
RestartRequired          : True
ShutdownRequired         : False
ClearRequired            : True
PhysicalPresenceRequired : True
```

This command initializes a TPM.
The **ForceClearAllowed** parameter means that the owner authorization value needs to be imported or reset in order for provisioning to continue.
The **PhysicalPresenceAllowed** parameter means that a user must be present during a restart to continue the process.

The cmdlet returns an object with information about the state of the provisioning process.

## PARAMETERS

### -AllowClear
Indicates that the provisioning process clears the TPM, if necessary, to move the TPM closer to complying with Windows Server® 2012 standards.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: c

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowPhysicalPresence
Indicates that the provisioning process may send physical presence commands that require a user to be present in order to continue.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: p

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SwitchParameter

## OUTPUTS

### TpmProvisioningObject
This cmdlet returns a **TpmProvisioningObject** object that includes the following information:

- TpmReady. Whether the TPM is complies with Windows Server® 2012 standards.
- RestartRequired. Whether the computer requires a restart to continue the provisioning process.
- ShutdownRequired. Whether the computer must be shut down to continue the provisioning process.
- ClearRequired. If this has a value of **True**, you must import an owner authorization value or remove the owner authorization value. 
- PhysicalPresenceRequired. Whether a person must be at the computer during restart to continue the provisioning process.

## NOTES

## RELATED LINKS

[Clear-Tpm](./Clear-Tpm.md)

[Get-Tpm](./Get-Tpm.md)

[Unblock-Tpm](./Unblock-Tpm.md)

