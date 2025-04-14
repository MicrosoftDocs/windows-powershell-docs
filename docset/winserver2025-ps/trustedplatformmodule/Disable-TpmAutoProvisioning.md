---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/disable-tpmautoprovisioning?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-TpmAutoProvisioning
---

# Disable-TpmAutoProvisioning

## SYNOPSIS
Disables TPM auto-provisioning.

## SYNTAX

```
Disable-TpmAutoProvisioning [-OnlyForNextRestart] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-TpmAutoProvisioning** cmdlet disables Trusted Platform Module (TPM) auto-provisioning.
Provisioning is the process of preparing a TPM to be used.
You can disable provisioning completely or only for the next restart.
You can use the Enable-TpmAutoProvisioning cmdlet to enable auto-provisioning.

For more information on TPM, see [Trusted Platform Module Technology Overview](/windows/security/information-protection/tpm/trusted-platform-module-overview).

## EXAMPLES

### Example 1: Disable auto-provisioning
```
PS C:\> Disable-TpmAutoProvisioning
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : OwnerClearDisabled : True
AutoProvisioning   : Disabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command disables TPM auto-provisioning.
You can use the **Enable-TpmAutoProvisioning** cmdlet to enable auto-provisioning.

### Example 2: Disable auto-provisioning for next restart
```
PS C:\> Disable-TpmAutoProvisioning -OnlyForNextRestart
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : OwnerClearDisabled : True
AutoProvisioning   : DisabledForNextBoot
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command disables TPM auto-provisioning for the next restart.
In the next restart after that, auto-provisioning continues.

## PARAMETERS

### -OnlyForNextRestart
Indicates that the cmdlet disables auto-provisioning only for the next computer restart.
During the restart after that, auto-provisioning begins.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: b

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SwitchParameter

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

[Enable-TpmAutoProvisioning](./Enable-TpmAutoProvisioning.md)

