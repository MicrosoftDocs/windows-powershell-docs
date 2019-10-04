---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-TpmAutoProvisioning
ms.reviewer:
ms.assetid: 20939446-FC0F-44A7-901E-365868E7BDA9
---

# Enable-TpmAutoProvisioning

## SYNOPSIS
Enables TPM auto-provisioning.

## SYNTAX

```
Enable-TpmAutoProvisioning [<CommonParameters>]
```

## DESCRIPTION
The **Enable-TpmAutoProvisioning** cmdlet enables Trusted Platform Module (TPM) provisioning to occur during auto-provisioning.
Provisioning is the process of preparing a TPM to be used.
You can use the Disable-TpmAutoProvisioning cmdlet to prevent auto-provisioning, either permanently or for the next restart.

For more information on TPM, see the [Trusted Platform Module Technology Overview](http://technet.microsoft.com/en-us/library/jj131725.aspx) in the Technet library.

## EXAMPLES

### Example 1: Enable auto-provisioning
```
PS C:\> Enable-TpmAutoProvisioning
TpmReady           : False
TpmPresent         : True
ManagedAuthLevel   : Full
OwnerAuth          : OwnerClearDisabled : True
AutoProvisioning   : Enabled
LockedOut          : False
SelfTest           : {191, 191, 245, 191...}
```

This command enables auto-provisioning for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### TpmObject
This cmdlet returns a **TpmObject** object that contains the following information:

- TpmReady. Whether a TPM complies with Windows Server® 2012 standards.
- TpmPresent. Whether there is a TMP on the current computer.
- ManagedAuthLevel. The level at which the operating system manages the owner authorization. Possible values are Legacy, Balanced, and Full.
- OwnerClearDisabled. Whether TPM can be reset. If this value is **True**, the TPM cannot be reset through the operating system by using the owner authorization value. If this value is **False**, the TPM can be reset through the operating system. 
- AutoProvisioning. Whether the computer can use auto-provisioning. Possible values are NotDefined, Enabled, Disabled, and DisabledForNextBoot.
- LockedOut. Whether a TPM is locked out.
- SelfTest. Information returned by a test that TPM runs.

## NOTES

## RELATED LINKS

[Disable-TpmAutoProvisioning](./Disable-TpmAutoProvisioning.md)

