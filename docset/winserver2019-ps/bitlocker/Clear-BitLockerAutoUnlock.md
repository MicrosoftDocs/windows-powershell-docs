---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
manager: jasgro
Module Name: BitLocker
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/bitlocker/clear-bitlockerautounlock?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-BitLockerAutoUnlock
---

# Clear-BitLockerAutoUnlock

## SYNOPSIS
Removes BitLocker automatic unlocking keys.

## SYNTAX

```
Clear-BitLockerAutoUnlock [<CommonParameters>]
```

## DESCRIPTION
The **Clear-BitLockerAutoUnlock** cmdlet removes all automatic unlocking keys used by BitLocker Drive Encryption.
BitLocker stores these keys for the fixed data drives of a system on a volume that hosts a BitLocker-enabled operating system volume so that it can automatically unlock the fixed and removable data volumes in a system.
This makes it easier for users to access data volumes.

You can configure BitLocker to automatically unlock volumes that do not host an operating system.
After a user unlocks the operating system volume, BitLocker uses encrypted information stored in the registry and volume metadata to unlock any data volumes that use automatic unlocking.

You must remove automatic unlocking keys before you can disable BitLocker by using the **Disable-BitLocker** cmdlet.
You can use the **Disable-BitLockerAutoUnlock** cmdlet to remove keys for specific volumes that use automatic unlocking instead of all volumes.

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Clear automatic unlocking keys
```
PS C:\>Clear-BitLockerAutoUnlock
```

This command clears all automatic unlocking keys stored on the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### BitLockerVolume

## NOTES

## RELATED LINKS

[Disable-BitLockerAutoUnlock](./Disable-BitLockerAutoUnlock.md)

[Enable-BitLockerAutoUnlock](./Enable-BitLockerAutoUnlock.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

