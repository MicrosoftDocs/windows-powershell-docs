---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
Module Name: BitLocker
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitlocker/get-bitlockervolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BitLockerVolume
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

- VolumeType - Data or Operating System.
- Mount Point - Drive letter.
- CapacityGB - Size of drive.
- MetadataVersion - Returns the FVE metadata version of the volume.
    - 0 - **Unknown** - The operating system is unknown.
    - 1 - **Vista** - Windows Vista format, meaning that the volume was protected with BitLocker on a computer running Windows Vista.
    - 2 - **Win7** - Windows 7 format, meaning that the volume was protected with BitLocker on a computer running Windows 7 or the metadata format was upgraded by using the UpgradeVolume method.
- VolumeStatus - Whether BitLocker currently protects some, all, or none of the data on the volume.
- Encryption Percentage - Percent of the volume protected by BitLocker.
- KeyProtector - Type of key protector or protectors.
- AutoUnlock Enabled - Whether BitLocker uses automatic unlocking for the volume.
- Protection Status - Whether BitLocker currently uses a key protector to encrypt the volume encryption key.
- EncryptionMethod - Indicates the encryption algorithm and key size used on the volume.

See [BitLocker Overview](/windows/security/information-protection/bitlocker/bitlocker-overview) for more information.

For an overview of encryption methods, see [GetEncryptionMethod method](/windows/win32/secprov/getencryptionmethod-win32-encryptablevolume).

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

### Example 3: Get all attributes for a specific BitLocker volume
```
PS C:\> Get-BitLockerVolume -MountPoint C | Format-List
ComputerName         : DESKTOP-XXXXXXX
MountPoint           : C:
EncryptionMethod     : XtsAes128
AutoUnlockEnabled    :
AutoUnlockKeyStored  : False
MetadataVersion      : 2
VolumeStatus         : FullyEncrypted
ProtectionStatus     : On
LockStatus           : Unlocked
EncryptionPercentage : 100
WipePercentage       : 0
VolumeType           : OperatingSystem
CapacityGB           : 218,2344
KeyProtector         : {RecoveryPassword, Tpm}
```

This command lists all BitLocker related attributes for C drive.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Add-BitLockerKeyProtector](./Add-BitLockerKeyProtector.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Enable-BitLockerAutoUnlock](./Enable-BitLockerAutoUnlock.md)
