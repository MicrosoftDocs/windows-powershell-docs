---
external help file: BitLocker-help.xml
Module Name: BitLocker
online version: 
schema: 2.0.0
title: Clear-BitLockerAutoUnlock
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D39F712B-7DCC-4F4D-BE51-449D7F5647E6
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

You must remove automatic unlocking keys before you can disable BitLocker by using the Disable-BitLocker cmdlet.
You can use the Disable-BitLockerAutoUnlock cmdlet to remove keys for specific volumes that use automatic unlocking instead of all volumes.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Clear automatic unlocking keys
```
PS C:\>Clear-BitLockerAutoUnlock
```

This command clears all automatic unlocking keys stored on the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### BitLockerVolume

## NOTES

## RELATED LINKS

[Disable-BitLockerAutoUnlock](./Disable-BitLockerAutoUnlock.md)

[Enable-BitLockerAutoUnlock](./Enable-BitLockerAutoUnlock.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

