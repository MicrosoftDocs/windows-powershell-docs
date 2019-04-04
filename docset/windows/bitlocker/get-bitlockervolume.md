---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: kenwith
author: kenwith
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-BitLockerVolume
ms.reviewer:
ms.assetid: 0714E33E-71B1-4FDE-8B83-25F50135874B
---

# Get-BitLockerVolume

## SYNOPSIS
Gets information about volumes that BitLocker can protect.

## SYNTAX

```
Get-BitLockerVolume [[-MountPoint] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BitLockerVolume** cmdlet gets information about volumes that BitLocker Drive Encryption can protect.
You can specify a BitLocker volume by drive letter, followed by a colon (C:, E:).
If you do not specify a drive letter, this cmdlet gets all volumes for the current computer.

You can use this cmdlet to get BitLocker volumes to use with other cmdlets, such as the **Enable-BitLocker** cmdlet or the **Add-BitLockerKeyProtector** cmdlet.
You can also use this cmdlet to view the following information about a BitLocker volume: 

- VolumeType.
Data or Operating System.
- Mount Point.
Drive letter.
- CapacityGB.
Size of drive.
- VolumeStatus.
Whether BitLocker currently protects some, all, or none of the data on the volume. 
- Encryption Percentage.
Percent of the volume protected by BitLocker.
- KeyProtector.
Type of key protector or protectors.
- AutoUnlock Enabled.
Whether BitLocker uses automatic unlocking for the volume.
- Protection Status.
Whether BitLocker currently uses a key protector to encrypt the volume encryption key.

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Get all BitLocker volumes
```
PS C:\> Get-BitLockerVolume 

VolumeType      Mount CapacityGB VolumeStatus           Encryption KeyProtector              AutoUnlock Protection
                Point                                   Percentage                           Enabled    Status
----------      ----- ---------- ------------           ---------- ------------              ---------- ----------
Data            D:        931.51 EncryptionInProgress   1          {RecoveryPassword, Pas...            Off
Data            E:        928.83 FullyDecrypted         0          {}                                   Off
OperatingSystem C:        232.54 FullyDecrypted         0          {Tpm}                                Off
Data            F:          0.98 FullyDecrypted         0          {}                                   Off
Data            G:          1.70 FullyDecrypted         0          {}                                   Off
```

This command gets all the BitLocker volumes for the current computer.

### Example 2: Get a specific BitLocker volume
```
PS C:\> Get-BitLockerVolume -MountPoint "E:"

VolumeType      Mount CapacityGB VolumeStatus           Encryption KeyProtector              AutoUnlock Protection
                Point                                   Percentage                           Enabled    Status
----------      ----- ---------- ------------           ---------- ------------              ---------- ----------
Data            E:        928.83 FullyDecrypted         0          {}                                   Off
```

This command gets the specified BitLocker volume.

## PARAMETERS

### -MountPoint
Specifies an array of drive letters.
This cmdlet gets these BitLocker volumes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Add-BitLockerKeyProtector](./Add-BitLockerKeyProtector.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Enable-BitLockerAutoUnlock](./Enable-BitLockerAutoUnlock.md)
