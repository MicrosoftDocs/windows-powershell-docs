---
author: Kateyanne
description: 
external help file: BitLocker-help.xml
manager: jasgro
Module Name: BitLocker
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/bitlocker/enable-bitlockerautounlock?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-BitLockerAutoUnlock
---

# Enable-BitLockerAutoUnlock

## SYNOPSIS
Enables automatic unlocking for a BitLocker volume.

## SYNTAX

```
Enable-BitLockerAutoUnlock [-MountPoint] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-BitLockerAutoUnlock** cmdlet enables automatic unlocking for a volume protected by BitLocker Disk Encryption.

You can configure BitLocker to automatically unlock volumes that do not host an operating system.
After a user unlocks the operating system volume, BitLocker uses encrypted information stored in the registry and volume metadata to unlock any data volumes that use automatic unlocking.

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).

## EXAMPLES

### Example 1: Enable automatic unlocking
```
PS C:\>Enable-BitLockerAutoUnlock -MountPoint "E:"
```

This command enables automatic unlocking for the specified BitLocker volume.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet enables automatic unlocking for the volumes specified.
To obtain a BitLocker volume object, use the Get-BitLockerVolume cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Clear-BitLockerAutoUnlock](./Clear-BitLockerAutoUnlock.md)

[Disable-BitLockerAutoUnlock](./Disable-BitLockerAutoUnlock.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

